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
ms.openlocfilehash: 52544619171dbc7034baeb5feb61395d81096387
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400253"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="b18f9-102">Proprietà axis descendant XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b18f9-102">XML Descendant Axis Property (Visual Basic)</span></span>

<span data-ttu-id="b18f9-103">Fornisce l'accesso ai discendenti dei seguenti elementi: un <xref:System.Xml.Linq.XElement> oggetto, un <xref:System.Xml.Linq.XDocument> oggetto, una raccolta di <xref:System.Xml.Linq.XElement> oggetti o una raccolta di <xref:System.Xml.Linq.XDocument> oggetti.</span><span class="sxs-lookup"><span data-stu-id="b18f9-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="b18f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b18f9-104">Syntax</span></span>

```vb
object...<descendant>
```

## <a name="parts"></a><span data-ttu-id="b18f9-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b18f9-105">Parts</span></span>

<span data-ttu-id="b18f9-106">`object` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b18f9-106">`object` Required.</span></span> <span data-ttu-id="b18f9-107">Un oggetto <xref:System.Xml.Linq.XElement>, un oggetto <xref:System.Xml.Linq.XDocument>, una raccolta di oggetti <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="b18f9-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

<span data-ttu-id="b18f9-108">`...<` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b18f9-108">`...<` Required.</span></span> <span data-ttu-id="b18f9-109">Indica l'inizio di una proprietà asse discendente.</span><span class="sxs-lookup"><span data-stu-id="b18f9-109">Denotes the start of a descendant axis property.</span></span>

<span data-ttu-id="b18f9-110">`descendant` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b18f9-110">`descendant` Required.</span></span> <span data-ttu-id="b18f9-111">Nome dei nodi discendenti a cui accedere, nel formato [ `prefix:]name` .</span><span class="sxs-lookup"><span data-stu-id="b18f9-111">Name of the descendant nodes to access, of the form [`prefix:]name`.</span></span>

|<span data-ttu-id="b18f9-112">Parte</span><span class="sxs-lookup"><span data-stu-id="b18f9-112">Part</span></span>|<span data-ttu-id="b18f9-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b18f9-113">Description</span></span>|
|----------|-----------------|
|`prefix`|<span data-ttu-id="b18f9-114">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="b18f9-114">Optional.</span></span> <span data-ttu-id="b18f9-115">Prefisso dello spazio dei nomi XML per il nodo discendente.</span><span class="sxs-lookup"><span data-stu-id="b18f9-115">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="b18f9-116">Deve essere uno spazio dei nomi XML globale definito usando un' `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b18f9-116">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|
|`name`|<span data-ttu-id="b18f9-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b18f9-117">Required.</span></span> <span data-ttu-id="b18f9-118">Nome locale del nodo discendente.</span><span class="sxs-lookup"><span data-stu-id="b18f9-118">Local name of the descendant node.</span></span> <span data-ttu-id="b18f9-119">Vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b18f9-119">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|

<span data-ttu-id="b18f9-120">`>` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b18f9-120">`>` Required.</span></span> <span data-ttu-id="b18f9-121">Indica la fine di una proprietà asse discendente.</span><span class="sxs-lookup"><span data-stu-id="b18f9-121">Denotes the end of a descendant axis property.</span></span>

## <a name="return-value"></a><span data-ttu-id="b18f9-122">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b18f9-122">Return Value</span></span>

<span data-ttu-id="b18f9-123">Una raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="b18f9-123">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="remarks"></a><span data-ttu-id="b18f9-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="b18f9-124">Remarks</span></span>

<span data-ttu-id="b18f9-125">È possibile utilizzare una proprietà axis discendente XML per accedere ai nodi discendenti in base al nome di un <xref:System.Xml.Linq.XElement> oggetto o oppure <xref:System.Xml.Linq.XDocument> da una raccolta di <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> oggetti o.</span><span class="sxs-lookup"><span data-stu-id="b18f9-125">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="b18f9-126">Utilizzare la `Value` proprietà XML per accedere al valore del primo nodo discendente nella raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="b18f9-126">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="b18f9-127">Per ulteriori informazioni, vedere [proprietà del valore XML](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="b18f9-127">For more information, see [XML Value Property](xml-value-property.md).</span></span>

<span data-ttu-id="b18f9-128">Il compilatore Visual Basic converte le proprietà dell'asse discendente in chiamate al <xref:System.Xml.Linq.XContainer.Descendants%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b18f9-128">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="b18f9-129">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="b18f9-129">XML Namespaces</span></span>

<span data-ttu-id="b18f9-130">Il nome in una proprietà asse discendente può utilizzare solo spazi dei nomi XML dichiarati globalmente con l' `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b18f9-130">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="b18f9-131">Non può utilizzare spazi dei nomi XML dichiarati localmente nei valori letterali degli elementi XML.</span><span class="sxs-lookup"><span data-stu-id="b18f9-131">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="b18f9-132">Per altre informazioni, vedere [istruzione Imports (spazio dei nomi XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b18f9-132">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>

## <a name="example"></a><span data-ttu-id="b18f9-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="b18f9-133">Example</span></span>

<span data-ttu-id="b18f9-134">Nell'esempio seguente viene illustrato come accedere al valore del primo nodo discendente denominato `name` e ai valori di tutti i nodi discendenti denominati `phone` dall' `contacts` oggetto.</span><span class="sxs-lookup"><span data-stu-id="b18f9-134">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

<span data-ttu-id="b18f9-135">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="b18f9-135">This code displays the following text:</span></span>

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a><span data-ttu-id="b18f9-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="b18f9-136">Example</span></span>

<span data-ttu-id="b18f9-137">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="b18f9-137">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="b18f9-138">USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e accedere al valore del primo nodo figlio con il nome completo `ns:name` .</span><span class="sxs-lookup"><span data-stu-id="b18f9-138">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

<span data-ttu-id="b18f9-139">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="b18f9-139">This code displays the following text:</span></span>

`Name: Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="b18f9-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b18f9-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="b18f9-141">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="b18f9-141">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="b18f9-142">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="b18f9-142">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="b18f9-143">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b18f9-143">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="b18f9-144">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="b18f9-144">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
