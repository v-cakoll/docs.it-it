---
title: XML Descendant Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: b2bf524214fa8ecca215d50c198b23d127e3b400
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349441"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="2fb86-102">Proprietà axis descendant XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fb86-102">XML Descendant Axis Property (Visual Basic)</span></span>

<span data-ttu-id="2fb86-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span><span class="sxs-lookup"><span data-stu-id="2fb86-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="2fb86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2fb86-104">Syntax</span></span>

```vb
object...<descendant>
```

## <a name="parts"></a><span data-ttu-id="2fb86-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2fb86-105">Parts</span></span>

<span data-ttu-id="2fb86-106">`object` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2fb86-106">`object` Required.</span></span> <span data-ttu-id="2fb86-107">Un oggetto <xref:System.Xml.Linq.XElement>, un oggetto <xref:System.Xml.Linq.XDocument>, una raccolta di oggetti <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="2fb86-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

<span data-ttu-id="2fb86-108">`...<` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2fb86-108">`...<` Required.</span></span> <span data-ttu-id="2fb86-109">Denotes the start of a descendant axis property.</span><span class="sxs-lookup"><span data-stu-id="2fb86-109">Denotes the start of a descendant axis property.</span></span>

<span data-ttu-id="2fb86-110">`descendant` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2fb86-110">`descendant` Required.</span></span> <span data-ttu-id="2fb86-111">Name of the descendant nodes to access, of the form [`prefix:]name`.</span><span class="sxs-lookup"><span data-stu-id="2fb86-111">Name of the descendant nodes to access, of the form [`prefix:]name`.</span></span>

|<span data-ttu-id="2fb86-112">Parte</span><span class="sxs-lookup"><span data-stu-id="2fb86-112">Part</span></span>|<span data-ttu-id="2fb86-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2fb86-113">Description</span></span>|
|----------|-----------------|
|`prefix`|<span data-ttu-id="2fb86-114">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2fb86-114">Optional.</span></span> <span data-ttu-id="2fb86-115">XML namespace prefix for the descendant node.</span><span class="sxs-lookup"><span data-stu-id="2fb86-115">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="2fb86-116">Must be a global XML namespace that is defined by using an `Imports` statement.</span><span class="sxs-lookup"><span data-stu-id="2fb86-116">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|
|`name`|<span data-ttu-id="2fb86-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2fb86-117">Required.</span></span> <span data-ttu-id="2fb86-118">Local name of the descendant node.</span><span class="sxs-lookup"><span data-stu-id="2fb86-118">Local name of the descendant node.</span></span> <span data-ttu-id="2fb86-119">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="2fb86-119">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|

<span data-ttu-id="2fb86-120">`>` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2fb86-120">`>` Required.</span></span> <span data-ttu-id="2fb86-121">Denotes the end of a descendant axis property.</span><span class="sxs-lookup"><span data-stu-id="2fb86-121">Denotes the end of a descendant axis property.</span></span>

## <a name="return-value"></a><span data-ttu-id="2fb86-122">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2fb86-122">Return Value</span></span>

<span data-ttu-id="2fb86-123">Raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="2fb86-123">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="remarks"></a><span data-ttu-id="2fb86-124">Note</span><span class="sxs-lookup"><span data-stu-id="2fb86-124">Remarks</span></span>

<span data-ttu-id="2fb86-125">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span><span class="sxs-lookup"><span data-stu-id="2fb86-125">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="2fb86-126">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span><span class="sxs-lookup"><span data-stu-id="2fb86-126">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="2fb86-127">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="2fb86-127">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>

<span data-ttu-id="2fb86-128">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span><span class="sxs-lookup"><span data-stu-id="2fb86-128">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="2fb86-129">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="2fb86-129">XML Namespaces</span></span>

<span data-ttu-id="2fb86-130">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span><span class="sxs-lookup"><span data-stu-id="2fb86-130">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="2fb86-131">It cannot use XML namespaces declared locally within XML element literals.</span><span class="sxs-lookup"><span data-stu-id="2fb86-131">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="2fb86-132">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="2fb86-132">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

## <a name="example"></a><span data-ttu-id="2fb86-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="2fb86-133">Example</span></span>

<span data-ttu-id="2fb86-134">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span><span class="sxs-lookup"><span data-stu-id="2fb86-134">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

<span data-ttu-id="2fb86-135">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="2fb86-135">This code displays the following text:</span></span>

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a><span data-ttu-id="2fb86-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="2fb86-136">Example</span></span>

<span data-ttu-id="2fb86-137">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="2fb86-137">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="2fb86-138">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="2fb86-138">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

<span data-ttu-id="2fb86-139">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="2fb86-139">This code displays the following text:</span></span>

`Name: Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="2fb86-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fb86-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="2fb86-141">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="2fb86-141">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="2fb86-142">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="2fb86-142">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="2fb86-143">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2fb86-143">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="2fb86-144">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="2fb86-144">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
