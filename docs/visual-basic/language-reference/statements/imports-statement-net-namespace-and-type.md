---
title: Istruzione Imports-tipo e spazio dei nomi .NET (Visual Basic)
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
ms.openlocfilehash: a0b7a6a5fd16dc0daa620e6b490ddfdeb0e7c80e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912383"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="793be-102">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="793be-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="793be-103">Consente di fare riferimento ai nomi dei tipi senza qualifica dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="793be-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="793be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="793be-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="793be-105">Parti</span><span class="sxs-lookup"><span data-stu-id="793be-105">Parts</span></span>  
  
|<span data-ttu-id="793be-106">Termine</span><span class="sxs-lookup"><span data-stu-id="793be-106">Term</span></span>|<span data-ttu-id="793be-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="793be-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="793be-108">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="793be-108">Optional.</span></span> <span data-ttu-id="793be-109">Alias o nome di *importazione* a `namespace` cui il codice può fare riferimento al posto della stringa di qualificazione completa.</span><span class="sxs-lookup"><span data-stu-id="793be-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="793be-110">Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="793be-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="793be-111">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="793be-111">Required.</span></span> <span data-ttu-id="793be-112">Nome completo dello spazio dei nomi importato.</span><span class="sxs-lookup"><span data-stu-id="793be-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="793be-113">Può essere una stringa di spazi dei nomi annidati a qualsiasi livello.</span><span class="sxs-lookup"><span data-stu-id="793be-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="793be-114">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="793be-114">Optional.</span></span> <span data-ttu-id="793be-115">Nome di un elemento di programmazione dichiarato nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="793be-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="793be-116">Può essere qualsiasi elemento contenitore.</span><span class="sxs-lookup"><span data-stu-id="793be-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="793be-117">Note</span><span class="sxs-lookup"><span data-stu-id="793be-117">Remarks</span></span>  
 <span data-ttu-id="793be-118">L' `Imports` istruzione consente di fare riferimento direttamente ai tipi contenuti in un determinato spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="793be-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="793be-119">È possibile specificare un singolo nome di spazio dei nomi o una stringa di spazi dei nomi annidati.</span><span class="sxs-lookup"><span data-stu-id="793be-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="793be-120">Ogni spazio dei nomi annidato è separato dallo spazio dei nomi di livello superiore`.`successivo per un punto (), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="793be-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="793be-121">Ogni file di origine può contenere un numero `Imports` qualsiasi di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="793be-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="793be-122">Devono seguire qualsiasi dichiarazione di opzione, ad esempio l' `Option Strict` istruzione, e devono precedere qualsiasi dichiarazione di elemento di programmazione, `Module` ad esempio istruzioni o `Class` .</span><span class="sxs-lookup"><span data-stu-id="793be-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="793be-123">È possibile usare `Imports` solo a livello di file.</span><span class="sxs-lookup"><span data-stu-id="793be-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="793be-124">Ciò significa che il contesto di dichiarazione per l'importazione deve essere un file di origine e non può essere uno spazio dei nomi, una classe, una struttura, un modulo, un'interfaccia, una routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="793be-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="793be-125">Si noti che `Imports` l'istruzione non rende disponibili gli elementi di altri progetti e assembly per il progetto.</span><span class="sxs-lookup"><span data-stu-id="793be-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="793be-126">L'importazione non comporta l'impostazione di un riferimento.</span><span class="sxs-lookup"><span data-stu-id="793be-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="793be-127">Rimuove solo la necessità di qualificare i nomi già disponibili per il progetto.</span><span class="sxs-lookup"><span data-stu-id="793be-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="793be-128">Per ulteriori informazioni, vedere "importazione di elementi contenitore" in [riferimenti a elementi](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)dichiarati.</span><span class="sxs-lookup"><span data-stu-id="793be-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="793be-129">È possibile definire istruzioni `Imports` implicite usando la [pagina riferimenti, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="793be-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="793be-130">Per altre informazioni, vedere [Procedura: Aggiungere o rimuovere spazi dei nomi importati](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="793be-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="793be-131">Alias di importazione</span><span class="sxs-lookup"><span data-stu-id="793be-131">Import Aliases</span></span>  
 <span data-ttu-id="793be-132">Un *alias di importazione* definisce l'alias per uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="793be-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="793be-133">Gli alias di importazione sono utili quando è necessario usare elementi con lo stesso nome dichiarati in uno o più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="793be-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="793be-134">Per ulteriori informazioni e un esempio, vedere "qualificazione di un nome di elemento" in [riferimenti a elementi](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)dichiarati.</span><span class="sxs-lookup"><span data-stu-id="793be-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="793be-135">Non è consigliabile dichiarare un membro a livello di modulo con lo stesso nome `aliasname`di.</span><span class="sxs-lookup"><span data-stu-id="793be-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="793be-136">In tal caso, il compilatore Visual Basic utilizza `aliasname` solo per il membro dichiarato e non lo riconosce più come alias di importazione.</span><span class="sxs-lookup"><span data-stu-id="793be-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="793be-137">Sebbene la sintassi utilizzata per dichiarare un alias di importazione sia simile a quella utilizzata per l'importazione di un prefisso dello spazio dei nomi XML, i risultati sono diversi.</span><span class="sxs-lookup"><span data-stu-id="793be-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="793be-138">Un alias di importazione può essere usato come espressione nel codice, mentre un prefisso dello spazio dei nomi XML può essere usato solo nei valori letterali XML o nelle proprietà Axis XML come prefisso per un nome di attributo o di elemento completo.</span><span class="sxs-lookup"><span data-stu-id="793be-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="793be-139">Nomi di elementi</span><span class="sxs-lookup"><span data-stu-id="793be-139">Element Names</span></span>  
 <span data-ttu-id="793be-140">Se si specifica `element`, deve rappresentare un *elemento contenitore*, ovvero un elemento di programmazione che può contenere altri elementi.</span><span class="sxs-lookup"><span data-stu-id="793be-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="793be-141">Gli elementi contenitore includono classi, strutture, moduli, interfacce ed enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="793be-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="793be-142">L'ambito degli elementi resi disponibili da un' `Imports` istruzione varia a seconda che si specifichi. `element`</span><span class="sxs-lookup"><span data-stu-id="793be-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="793be-143">Se si specificano `namespace`solo, tutti i membri denominati in modo univoco dello spazio dei nomi e i membri degli elementi contenitore all'interno di tale spazio dei nomi sono disponibili senza qualificazione.</span><span class="sxs-lookup"><span data-stu-id="793be-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="793be-144">Se si specificano `namespace` sia `element`che, solo i membri di tale elemento saranno disponibili senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="793be-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="793be-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="793be-145">Example</span></span>  
 <span data-ttu-id="793be-146">Nell'esempio seguente vengono restituite tutte le cartelle in C:\ Directory tramite la <xref:System.IO.DirectoryInfo> classe.</span><span class="sxs-lookup"><span data-stu-id="793be-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="793be-147">Il codice non `Imports` contiene istruzioni all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="793be-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="793be-148">Pertanto, i `DirectoryInfo`riferimenti <xref:System.Text.StringBuilder>, e <xref:Microsoft.VisualBasic.ControlChars.CrLf> sono tutti completi con gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="793be-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="793be-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="793be-149">Example</span></span>  
 <span data-ttu-id="793be-150">Nell'esempio seguente vengono `Imports` incluse le istruzioni per gli spazi dei nomi a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="793be-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="793be-151">Pertanto, non è necessario che i tipi siano completi con gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="793be-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="793be-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="793be-152">Example</span></span>  
 <span data-ttu-id="793be-153">Nell'esempio seguente sono `Imports` incluse istruzioni che consentono di creare alias per gli spazi dei nomi a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="793be-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="793be-154">I tipi sono qualificati con gli alias.</span><span class="sxs-lookup"><span data-stu-id="793be-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="793be-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="793be-155">Example</span></span>  
 <span data-ttu-id="793be-156">Nell'esempio seguente sono `Imports` incluse istruzioni per la creazione di alias per i tipi a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="793be-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="793be-157">Gli alias vengono utilizzati per specificare i tipi.</span><span class="sxs-lookup"><span data-stu-id="793be-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="793be-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="793be-158">See also</span></span>

- [<span data-ttu-id="793be-159">Istruzione Namespace</span><span class="sxs-lookup"><span data-stu-id="793be-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="793be-160">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="793be-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="793be-161">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="793be-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="793be-162">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="793be-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="793be-163">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="793be-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
