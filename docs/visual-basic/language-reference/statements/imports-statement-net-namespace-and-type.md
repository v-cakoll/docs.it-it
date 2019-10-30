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
ms.openlocfilehash: 573bb7383b292e0ad2e85a4355d89cf92fe8dd7d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040731"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="d9f37-102">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="d9f37-102">Imports Statement (.NET Namespace and Type)</span></span>

<span data-ttu-id="d9f37-103">Consente di fare riferimento ai nomi dei tipi senza qualifica dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d9f37-103">Enables type names to be referenced without namespace qualification.</span></span>

## <a name="syntax"></a><span data-ttu-id="d9f37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9f37-104">Syntax</span></span>

```vb
Imports [ aliasname = ] namespace
' -or-
Imports [ aliasname = ] namespace.element
```

## <a name="parts"></a><span data-ttu-id="d9f37-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d9f37-105">Parts</span></span>

|<span data-ttu-id="d9f37-106">Termine</span><span class="sxs-lookup"><span data-stu-id="d9f37-106">Term</span></span>|<span data-ttu-id="d9f37-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="d9f37-107">Definition</span></span>|
|---|---|
|`aliasname`|<span data-ttu-id="d9f37-108">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d9f37-108">Optional.</span></span> <span data-ttu-id="d9f37-109">*Alias di importazione* o nome con cui il codice può fare riferimento a `namespace` anziché alla stringa di qualificazione completa.</span><span class="sxs-lookup"><span data-stu-id="d9f37-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="d9f37-110">Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="d9f37-110">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`namespace`|<span data-ttu-id="d9f37-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d9f37-111">Required.</span></span> <span data-ttu-id="d9f37-112">Nome completo dello spazio dei nomi importato.</span><span class="sxs-lookup"><span data-stu-id="d9f37-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="d9f37-113">Può essere una stringa di spazi dei nomi annidati a qualsiasi livello.</span><span class="sxs-lookup"><span data-stu-id="d9f37-113">Can be a string of namespaces nested to any level.</span></span>|
|`element`|<span data-ttu-id="d9f37-114">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d9f37-114">Optional.</span></span> <span data-ttu-id="d9f37-115">Nome di un elemento di programmazione dichiarato nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d9f37-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="d9f37-116">Può essere qualsiasi elemento contenitore.</span><span class="sxs-lookup"><span data-stu-id="d9f37-116">Can be any container element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d9f37-117">Note</span><span class="sxs-lookup"><span data-stu-id="d9f37-117">Remarks</span></span>

<span data-ttu-id="d9f37-118">L'istruzione `Imports` consente di fare riferimento direttamente ai tipi contenuti in un determinato spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d9f37-118">The `Imports` statement enables types that are contained in a given namespace to be referenced directly.</span></span>

<span data-ttu-id="d9f37-119">È possibile specificare un singolo nome di spazio dei nomi o una stringa di spazi dei nomi annidati.</span><span class="sxs-lookup"><span data-stu-id="d9f37-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="d9f37-120">Ogni spazio dei nomi annidato è separato dallo spazio dei nomi di livello superiore successivo per un punto (`.`), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d9f37-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates:</span></span>

```vb
Imports System.Collections.Generic
```

<span data-ttu-id="d9f37-121">Ogni file di origine può contenere un numero qualsiasi di istruzioni `Imports`.</span><span class="sxs-lookup"><span data-stu-id="d9f37-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="d9f37-122">Devono seguire qualsiasi dichiarazione di opzione, ad esempio l'istruzione `Option Strict`, e devono precedere qualsiasi dichiarazione di elemento di programmazione, ad esempio `Module` o istruzioni `Class`.</span><span class="sxs-lookup"><span data-stu-id="d9f37-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>

<span data-ttu-id="d9f37-123">È possibile utilizzare `Imports` solo a livello di file.</span><span class="sxs-lookup"><span data-stu-id="d9f37-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="d9f37-124">Ciò significa che il contesto di dichiarazione per l'importazione deve essere un file di origine e non può essere uno spazio dei nomi, una classe, una struttura, un modulo, un'interfaccia, una routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="d9f37-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>

<span data-ttu-id="d9f37-125">Si noti che l'istruzione `Imports` non rende disponibili gli elementi di altri progetti e assembly per il progetto.</span><span class="sxs-lookup"><span data-stu-id="d9f37-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="d9f37-126">L'importazione non comporta l'impostazione di un riferimento.</span><span class="sxs-lookup"><span data-stu-id="d9f37-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="d9f37-127">Rimuove solo la necessità di qualificare i nomi già disponibili per il progetto.</span><span class="sxs-lookup"><span data-stu-id="d9f37-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="d9f37-128">Per ulteriori informazioni, vedere "importazione di elementi contenitore" in [riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="d9f37-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d9f37-129">È possibile definire istruzioni `Imports` implicite usando la [pagina riferimenti, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d9f37-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="d9f37-130">Per ulteriori informazioni, vedere [procedura: aggiungere o rimuovere spazi dei nomi importati (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d9f37-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>

## <a name="import-aliases"></a><span data-ttu-id="d9f37-131">Alias di importazione</span><span class="sxs-lookup"><span data-stu-id="d9f37-131">Import Aliases</span></span>

<span data-ttu-id="d9f37-132">Un *alias di importazione* definisce l'alias per uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="d9f37-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="d9f37-133">Gli alias di importazione sono utili quando è necessario usare elementi con lo stesso nome dichiarati in uno o più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d9f37-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="d9f37-134">Per ulteriori informazioni e un esempio, vedere "qualificazione di un nome di elemento" in [riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="d9f37-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

<span data-ttu-id="d9f37-135">Non dichiarare un membro a livello di modulo con lo stesso nome `aliasname`.</span><span class="sxs-lookup"><span data-stu-id="d9f37-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="d9f37-136">In tal caso, il compilatore Visual Basic utilizza `aliasname` solo per il membro dichiarato e non lo riconosce più come alias di importazione.</span><span class="sxs-lookup"><span data-stu-id="d9f37-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>

<span data-ttu-id="d9f37-137">Sebbene la sintassi utilizzata per dichiarare un alias di importazione sia simile a quella utilizzata per l'importazione di un prefisso dello spazio dei nomi XML, i risultati sono diversi.</span><span class="sxs-lookup"><span data-stu-id="d9f37-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="d9f37-138">Un alias di importazione può essere usato come espressione nel codice, mentre un prefisso dello spazio dei nomi XML può essere usato solo nei valori letterali XML o nelle proprietà Axis XML come prefisso per un nome di attributo o di elemento completo.</span><span class="sxs-lookup"><span data-stu-id="d9f37-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>

### <a name="element-names"></a><span data-ttu-id="d9f37-139">Nomi di elementi</span><span class="sxs-lookup"><span data-stu-id="d9f37-139">Element Names</span></span>

<span data-ttu-id="d9f37-140">Se si fornisce `element`, deve rappresentare un *elemento contenitore*, ovvero un elemento di programmazione che può contenere altri elementi.</span><span class="sxs-lookup"><span data-stu-id="d9f37-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="d9f37-141">Gli elementi contenitore includono classi, strutture, moduli, interfacce ed enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="d9f37-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>

<span data-ttu-id="d9f37-142">L'ambito degli elementi resi disponibili da un'istruzione `Imports` varia a seconda che si specifichino `element`.</span><span class="sxs-lookup"><span data-stu-id="d9f37-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="d9f37-143">Se si specificano solo `namespace`, tutti i membri denominati in modo univoco dello spazio dei nomi e i membri degli elementi contenitore all'interno di tale spazio dei nomi sono disponibili senza qualificazione.</span><span class="sxs-lookup"><span data-stu-id="d9f37-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="d9f37-144">Se si specificano sia `namespace` che `element`, solo i membri di tale elemento saranno disponibili senza qualificazione.</span><span class="sxs-lookup"><span data-stu-id="d9f37-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>

## <a name="example"></a><span data-ttu-id="d9f37-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9f37-145">Example</span></span>

<span data-ttu-id="d9f37-146">Nell'esempio seguente vengono restituite tutte le cartelle nella directory *C:\\* usando la classe <xref:System.IO.DirectoryInfo>:</span><span class="sxs-lookup"><span data-stu-id="d9f37-146">The following example returns all the folders in the *C:\\* directory by using the <xref:System.IO.DirectoryInfo> class:</span></span>

<span data-ttu-id="d9f37-147">Il codice non include istruzioni `Imports` all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="d9f37-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="d9f37-148">Pertanto, i riferimenti <xref:System.IO.DirectoryInfo>, <xref:System.Text.StringBuilder>e <xref:Microsoft.VisualBasic.ControlChars.CrLf> sono tutti completi con gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d9f37-148">Therefore, the <xref:System.IO.DirectoryInfo>, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>

[!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]

## <a name="example"></a><span data-ttu-id="d9f37-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9f37-149">Example</span></span>

<span data-ttu-id="d9f37-150">Nell'esempio seguente vengono incluse `Imports` istruzioni per gli spazi dei nomi a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="d9f37-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="d9f37-151">Pertanto, non è necessario che i tipi siano completi con gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d9f37-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>

[!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]

[!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]
  
## <a name="example"></a><span data-ttu-id="d9f37-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9f37-152">Example</span></span>

<span data-ttu-id="d9f37-153">Nell'esempio seguente vengono incluse `Imports` istruzioni che consentono di creare alias per gli spazi dei nomi a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="d9f37-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="d9f37-154">I tipi sono qualificati con gli alias.</span><span class="sxs-lookup"><span data-stu-id="d9f37-154">The types are qualified with the aliases.</span></span>

[!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]

[!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]

## <a name="example"></a><span data-ttu-id="d9f37-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9f37-155">Example</span></span>

<span data-ttu-id="d9f37-156">Nell'esempio seguente vengono incluse `Imports` istruzioni che consentono di creare alias per i tipi a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="d9f37-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="d9f37-157">Gli alias vengono utilizzati per specificare i tipi.</span><span class="sxs-lookup"><span data-stu-id="d9f37-157">Aliases are used to specify the types.</span></span>

[!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]

[!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]
  
## <a name="see-also"></a><span data-ttu-id="d9f37-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9f37-158">See also</span></span>

- [<span data-ttu-id="d9f37-159">Istruzione Namespace</span><span class="sxs-lookup"><span data-stu-id="d9f37-159">Namespace Statement</span></span>](namespace-statement.md)
- [<span data-ttu-id="d9f37-160">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9f37-160">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="d9f37-161">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="d9f37-161">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="d9f37-162">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="d9f37-162">Imports Statement (XML Namespace)</span></span>](imports-statement-xml-namespace.md)
- [<span data-ttu-id="d9f37-163">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="d9f37-163">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
