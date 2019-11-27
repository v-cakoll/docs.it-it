---
title: Istruzione Imports-spazio dei nomi XML
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 52864e4d1c8183b6243025e72368d23627049c84
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351057"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="72f90-102">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="72f90-102">Imports Statement (XML Namespace)</span></span>

<span data-ttu-id="72f90-103">Importa i prefissi degli spazi dei nomi XML da utilizzare nei valori letterali XML e nelle proprietà Axis XML.</span><span class="sxs-lookup"><span data-stu-id="72f90-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="72f90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72f90-104">Syntax</span></span>

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a><span data-ttu-id="72f90-105">Parti</span><span class="sxs-lookup"><span data-stu-id="72f90-105">Parts</span></span>

`xmlNamespacePrefix`  
<span data-ttu-id="72f90-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="72f90-106">Optional.</span></span> <span data-ttu-id="72f90-107">Stringa in base alla quale gli elementi e gli attributi XML possono fare riferimento `xmlNamespaceName`.</span><span class="sxs-lookup"><span data-stu-id="72f90-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="72f90-108">Se non viene specificato alcun `xmlNamespacePrefix`, lo spazio dei nomi XML importato è lo spazio dei nomi XML predefinito.</span><span class="sxs-lookup"><span data-stu-id="72f90-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="72f90-109">Deve essere un identificatore XML valido.</span><span class="sxs-lookup"><span data-stu-id="72f90-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="72f90-110">Per ulteriori informazioni, vedere [nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="72f90-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>

`xmlNamespaceName`  
<span data-ttu-id="72f90-111">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="72f90-111">Required.</span></span> <span data-ttu-id="72f90-112">Stringa che identifica lo spazio dei nomi XML importato.</span><span class="sxs-lookup"><span data-stu-id="72f90-112">The string identifying the XML namespace being imported.</span></span>

## <a name="remarks"></a><span data-ttu-id="72f90-113">Note</span><span class="sxs-lookup"><span data-stu-id="72f90-113">Remarks</span></span>

<span data-ttu-id="72f90-114">È possibile utilizzare l'istruzione `Imports` per definire gli spazi dei nomi XML globali che è possibile utilizzare con i valori letterali XML e le proprietà Axis XML o come parametri passati all'operatore `GetXmlNamespace`.</span><span class="sxs-lookup"><span data-stu-id="72f90-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="72f90-115">Per informazioni sull'utilizzo dell'istruzione `Imports` per importare un alias che può essere utilizzato nel caso in cui i nomi dei tipi vengano utilizzati nel codice, vedere [istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md). La sintassi per la dichiarazione di uno spazio dei nomi XML tramite l'istruzione `Imports` è identica a quella utilizzata in XML.</span><span class="sxs-lookup"><span data-stu-id="72f90-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="72f90-116">Pertanto, è possibile copiare una dichiarazione dello spazio dei nomi da un file XML e utilizzarla in un'istruzione `Imports`.</span><span class="sxs-lookup"><span data-stu-id="72f90-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>

<span data-ttu-id="72f90-117">I prefissi degli spazi dei nomi XML sono utili quando si desidera creare ripetutamente elementi XML che appartengono allo stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="72f90-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="72f90-118">Il prefisso dello spazio dei nomi XML dichiarato con l'istruzione `Imports` è globale nel senso che è disponibile per tutto il codice del file.</span><span class="sxs-lookup"><span data-stu-id="72f90-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="72f90-119">È possibile usarlo quando si creano valori letterali dell'elemento XML e quando si accede alle proprietà Axis XML.</span><span class="sxs-lookup"><span data-stu-id="72f90-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="72f90-120">Per altre informazioni, vedere [valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) e [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md).</span><span class="sxs-lookup"><span data-stu-id="72f90-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

<span data-ttu-id="72f90-121">Se si definisce uno spazio dei nomi XML globale senza prefisso dello spazio dei nomi (ad esempio, `Imports <xmlns="http://SomeNameSpace>"`), lo spazio dei nomi viene considerato lo spazio dei nomi XML predefinito.</span><span class="sxs-lookup"><span data-stu-id="72f90-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="72f90-122">Lo spazio dei nomi XML predefinito viene utilizzato per qualsiasi valore letterale elemento XML o proprietà asse degli attributi XML che non specificano in modo esplicito uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="72f90-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="72f90-123">Lo spazio dei nomi predefinito viene utilizzato anche se lo spazio dei nomi specificato è lo spazio dei nomi vuoto, ovvero `xmlns=""`.</span><span class="sxs-lookup"><span data-stu-id="72f90-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="72f90-124">Lo spazio dei nomi XML predefinito non si applica agli attributi XML nei valori letterali XML o alle proprietà axis dell'attributo XML che non dispongono di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="72f90-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>

<span data-ttu-id="72f90-125">Gli spazi dei nomi XML definiti in un valore letterale XML, denominati *spazi dei nomi XML locali*, hanno la precedenza sugli spazi dei nomi XML definiti dall'istruzione `Imports` come globale.</span><span class="sxs-lookup"><span data-stu-id="72f90-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="72f90-126">Gli spazi dei nomi XML definiti dall'istruzione `Imports` hanno la precedenza sugli spazi dei nomi XML importati per un progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="72f90-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="72f90-127">Se un valore letterale XML definisce uno spazio dei nomi XML, tale spazio dei nomi locale non si applica alle espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="72f90-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>

<span data-ttu-id="72f90-128">Gli spazi dei nomi XML globali seguono le stesse regole di definizione e definizione dell'ambito di .NET Framework spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="72f90-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="72f90-129">Di conseguenza, è possibile includere un'istruzione `Imports` per definire uno spazio dei nomi XML globale ovunque sia possibile importare uno spazio dei nomi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72f90-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="72f90-130">Sono inclusi i file di codice e gli spazi dei nomi importati a livello di progetto.</span><span class="sxs-lookup"><span data-stu-id="72f90-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="72f90-131">Per informazioni sugli spazi dei nomi importati a livello di progetto, vedere [pagina riferimenti, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="72f90-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>

<span data-ttu-id="72f90-132">Ogni file di origine può contenere un numero qualsiasi di istruzioni `Imports`.</span><span class="sxs-lookup"><span data-stu-id="72f90-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="72f90-133">Devono seguire le dichiarazioni di opzioni, ad esempio l'istruzione `Option Strict`, e devono precedere le dichiarazioni degli elementi di programmazione, ad esempio `Module` o `Class` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="72f90-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>

## <a name="example"></a><span data-ttu-id="72f90-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="72f90-134">Example</span></span>

<span data-ttu-id="72f90-135">Nell'esempio seguente viene importato uno spazio dei nomi XML predefinito e uno spazio dei nomi XML identificato con il prefisso `ns`.</span><span class="sxs-lookup"><span data-stu-id="72f90-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="72f90-136">Viene quindi creato un valore letterale XML che utilizza entrambi gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="72f90-136">It then creates XML literals that use both namespaces.</span></span>

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

<span data-ttu-id="72f90-137">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="72f90-137">This code displays the following text:</span></span>

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a><span data-ttu-id="72f90-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="72f90-138">Example</span></span>

<span data-ttu-id="72f90-139">Nell'esempio seguente viene importato il prefisso dello spazio dei nomi XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="72f90-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="72f90-140">Viene quindi creato un valore letterale XML che utilizza il prefisso dello spazio dei nomi e viene visualizzato il formato finale dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="72f90-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="72f90-141">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="72f90-141">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="72f90-142">Si noti che il compilatore ha convertito il prefisso dello spazio dei nomi XML da un prefisso globale a una definizione di prefisso locale.</span><span class="sxs-lookup"><span data-stu-id="72f90-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>

## <a name="example"></a><span data-ttu-id="72f90-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="72f90-143">Example</span></span>

<span data-ttu-id="72f90-144">Nell'esempio seguente viene importato il prefisso dello spazio dei nomi XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="72f90-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="72f90-145">Il prefisso dello spazio dei nomi viene quindi usato per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="72f90-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

<span data-ttu-id="72f90-146">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="72f90-146">This code displays the following text:</span></span>

`Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="72f90-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72f90-147">See also</span></span>

- [<span data-ttu-id="72f90-148">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="72f90-148">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="72f90-149">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="72f90-149">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="72f90-150">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="72f90-150">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="72f90-151">Operatore GetXmlNamespace</span><span class="sxs-lookup"><span data-stu-id="72f90-151">GetXmlNamespace Operator</span></span>](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
