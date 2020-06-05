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
ms.openlocfilehash: a3184d68b0e4cdff5d4296a5a638e22b4e83bcde
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404537"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="c26f4-102">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="c26f4-102">Imports Statement (XML Namespace)</span></span>

<span data-ttu-id="c26f4-103">Importa i prefissi degli spazi dei nomi XML da utilizzare nei valori letterali XML e nelle proprietà Axis XML.</span><span class="sxs-lookup"><span data-stu-id="c26f4-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="c26f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c26f4-104">Syntax</span></span>

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a><span data-ttu-id="c26f4-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c26f4-105">Parts</span></span>

`xmlNamespacePrefix`  
<span data-ttu-id="c26f4-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="c26f4-106">Optional.</span></span> <span data-ttu-id="c26f4-107">Stringa a cui possono fare riferimento gli elementi e gli attributi XML `xmlNamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="c26f4-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="c26f4-108">Se non `xmlNamespacePrefix` viene specificato alcun oggetto, lo spazio dei nomi XML importato sarà lo spazio dei nomi XML predefinito.</span><span class="sxs-lookup"><span data-stu-id="c26f4-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="c26f4-109">Deve essere un identificatore XML valido.</span><span class="sxs-lookup"><span data-stu-id="c26f4-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="c26f4-110">Per ulteriori informazioni, vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="c26f4-110">For more information, see [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>

`xmlNamespaceName`  
<span data-ttu-id="c26f4-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c26f4-111">Required.</span></span> <span data-ttu-id="c26f4-112">Stringa che identifica lo spazio dei nomi XML importato.</span><span class="sxs-lookup"><span data-stu-id="c26f4-112">The string identifying the XML namespace being imported.</span></span>

## <a name="remarks"></a><span data-ttu-id="c26f4-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="c26f4-113">Remarks</span></span>

<span data-ttu-id="c26f4-114">È possibile utilizzare l' `Imports` istruzione per definire gli spazi dei nomi XML globali che è possibile utilizzare con i valori letterali XML e le proprietà Axis XML o come parametri passati all' `GetXmlNamespace` operatore.</span><span class="sxs-lookup"><span data-stu-id="c26f4-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="c26f4-115">Per informazioni sull'uso dell' `Imports` istruzione per importare un alias che può essere usato in presenza di nomi di tipo nel codice, vedere [istruzione Imports (tipo e spazio dei nomi .NET)](imports-statement-net-namespace-and-type.md). La sintassi per la dichiarazione di uno spazio dei nomi XML tramite l' `Imports` istruzione è identica a quella utilizzata in XML.</span><span class="sxs-lookup"><span data-stu-id="c26f4-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="c26f4-116">Pertanto, è possibile copiare una dichiarazione dello spazio dei nomi da un file XML e utilizzarla in un' `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c26f4-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>

<span data-ttu-id="c26f4-117">I prefissi degli spazi dei nomi XML sono utili quando si desidera creare ripetutamente elementi XML che appartengono allo stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c26f4-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="c26f4-118">Il prefisso dello spazio dei nomi XML dichiarato con l' `Imports` istruzione è globale nel senso che è disponibile per tutto il codice del file.</span><span class="sxs-lookup"><span data-stu-id="c26f4-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="c26f4-119">È possibile usarlo quando si creano valori letterali dell'elemento XML e quando si accede alle proprietà Axis XML.</span><span class="sxs-lookup"><span data-stu-id="c26f4-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="c26f4-120">Per altre informazioni, vedere [valore letterale elemento XML](../xml-literals/xml-element-literal.md) e [Proprietà Axis XML](../xml-axis/index.md).</span><span class="sxs-lookup"><span data-stu-id="c26f4-120">For more information, see [XML Element Literal](../xml-literals/xml-element-literal.md) and [XML Axis Properties](../xml-axis/index.md).</span></span>

<span data-ttu-id="c26f4-121">Se si definisce uno spazio dei nomi XML globale senza un prefisso dello spazio dei nomi (ad esempio,), lo spazio dei nomi `Imports <xmlns="http://SomeNameSpace>"` viene considerato lo spazio dei nomi XML predefinito.</span><span class="sxs-lookup"><span data-stu-id="c26f4-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="c26f4-122">Lo spazio dei nomi XML predefinito viene utilizzato per qualsiasi valore letterale elemento XML o proprietà asse degli attributi XML che non specificano in modo esplicito uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c26f4-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="c26f4-123">Lo spazio dei nomi predefinito viene utilizzato anche se lo spazio dei nomi specificato è lo spazio dei nomi vuoto (ovvero `xmlns=""` ).</span><span class="sxs-lookup"><span data-stu-id="c26f4-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="c26f4-124">Lo spazio dei nomi XML predefinito non si applica agli attributi XML nei valori letterali XML o alle proprietà axis dell'attributo XML che non dispongono di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c26f4-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>

<span data-ttu-id="c26f4-125">Gli spazi dei nomi XML definiti in un valore letterale XML, denominati *spazi dei nomi XML locali*, hanno la precedenza sugli spazi dei nomi XML definiti dall' `Imports` istruzione come globali.</span><span class="sxs-lookup"><span data-stu-id="c26f4-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="c26f4-126">Gli spazi dei nomi XML definiti dall' `Imports` istruzione hanno la precedenza sugli spazi dei nomi XML importati per un progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c26f4-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="c26f4-127">Se un valore letterale XML definisce uno spazio dei nomi XML, tale spazio dei nomi locale non si applica alle espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="c26f4-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>

<span data-ttu-id="c26f4-128">Gli spazi dei nomi XML globali seguono le stesse regole di definizione e definizione dell'ambito di .NET Framework spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c26f4-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="c26f4-129">Di conseguenza, è possibile includere un' `Imports` istruzione per definire uno spazio dei nomi XML globale ovunque sia possibile importare uno spazio dei nomi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c26f4-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="c26f4-130">Sono inclusi i file di codice e gli spazi dei nomi importati a livello di progetto.</span><span class="sxs-lookup"><span data-stu-id="c26f4-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="c26f4-131">Per informazioni sugli spazi dei nomi importati a livello di progetto, vedere [pagina riferimenti, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c26f4-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>

<span data-ttu-id="c26f4-132">Ogni file di origine può contenere un numero qualsiasi di `Imports` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c26f4-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="c26f4-133">Devono seguire le dichiarazioni di opzioni, ad esempio l' `Option Strict` istruzione, e devono precedere le dichiarazioni degli elementi di programmazione, ad esempio le `Module` `Class` istruzioni o.</span><span class="sxs-lookup"><span data-stu-id="c26f4-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>

## <a name="example"></a><span data-ttu-id="c26f4-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="c26f4-134">Example</span></span>

<span data-ttu-id="c26f4-135">Nell'esempio seguente viene importato uno spazio dei nomi XML predefinito e uno spazio dei nomi XML identificato con il prefisso `ns` .</span><span class="sxs-lookup"><span data-stu-id="c26f4-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="c26f4-136">Viene quindi creato un valore letterale XML che utilizza entrambi gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c26f4-136">It then creates XML literals that use both namespaces.</span></span>

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

<span data-ttu-id="c26f4-137">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="c26f4-137">This code displays the following text:</span></span>

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a><span data-ttu-id="c26f4-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="c26f4-138">Example</span></span>

<span data-ttu-id="c26f4-139">Nell'esempio seguente viene importato il prefisso dello spazio dei nomi XML `ns` .</span><span class="sxs-lookup"><span data-stu-id="c26f4-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="c26f4-140">Viene quindi creato un valore letterale XML che utilizza il prefisso dello spazio dei nomi e viene visualizzato il formato finale dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="c26f4-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="c26f4-141">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="c26f4-141">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="c26f4-142">Si noti che il compilatore ha convertito il prefisso dello spazio dei nomi XML da un prefisso globale a una definizione di prefisso locale.</span><span class="sxs-lookup"><span data-stu-id="c26f4-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>

## <a name="example"></a><span data-ttu-id="c26f4-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="c26f4-143">Example</span></span>

<span data-ttu-id="c26f4-144">Nell'esempio seguente viene importato il prefisso dello spazio dei nomi XML `ns` .</span><span class="sxs-lookup"><span data-stu-id="c26f4-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="c26f4-145">Il prefisso dello spazio dei nomi viene quindi usato per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="c26f4-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

<span data-ttu-id="c26f4-146">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="c26f4-146">This code displays the following text:</span></span>

`Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="c26f4-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c26f4-147">See also</span></span>

- [<span data-ttu-id="c26f4-148">Valore letterale di elemento XML</span><span class="sxs-lookup"><span data-stu-id="c26f4-148">XML Element Literal</span></span>](../xml-literals/xml-element-literal.md)
- [<span data-ttu-id="c26f4-149">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="c26f4-149">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="c26f4-150">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="c26f4-150">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="c26f4-151">Operatore GetXmlNamespace</span><span class="sxs-lookup"><span data-stu-id="c26f4-151">GetXmlNamespace Operator</span></span>](../operators/getxmlnamespace-operator.md)
