---
title: Proprietà axis descendant XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: 3b8d13e606f28896cae88162d572470e49af3739
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730282"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="46a2d-102">Proprietà axis descendant XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46a2d-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="46a2d-103">Fornisce l'accesso ai discendenti di uno dei seguenti: un' <xref:System.Xml.Linq.XElement> oggetti, un' <xref:System.Xml.Linq.XDocument> oggetto, una raccolta di <xref:System.Xml.Linq.XElement> oggetti, oppure una raccolta di <xref:System.Xml.Linq.XDocument> oggetti.</span><span class="sxs-lookup"><span data-stu-id="46a2d-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a2d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46a2d-104">Syntax</span></span>  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="46a2d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="46a2d-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="46a2d-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="46a2d-106">Required.</span></span> <span data-ttu-id="46a2d-107">Un oggetto <xref:System.Xml.Linq.XElement>, un oggetto <xref:System.Xml.Linq.XDocument>, una raccolta di oggetti <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="46a2d-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="46a2d-108">...<</span><span class="sxs-lookup"><span data-stu-id="46a2d-108">...<</span></span>  
 <span data-ttu-id="46a2d-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="46a2d-109">Required.</span></span> <span data-ttu-id="46a2d-110">Indica l'inizio di una proprietà axis discendente.</span><span class="sxs-lookup"><span data-stu-id="46a2d-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="46a2d-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="46a2d-111">Required.</span></span> <span data-ttu-id="46a2d-112">Nome dei nodi discendente per accedere, nel formato [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="46a2d-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="46a2d-113">Parte</span><span class="sxs-lookup"><span data-stu-id="46a2d-113">Part</span></span>|<span data-ttu-id="46a2d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46a2d-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="46a2d-115">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="46a2d-115">Optional.</span></span> <span data-ttu-id="46a2d-116">Prefisso dello spazio dei nomi XML per il nodo discendente.</span><span class="sxs-lookup"><span data-stu-id="46a2d-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="46a2d-117">Deve essere uno spazio dei nomi XML globale definito usando un' `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="46a2d-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="46a2d-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="46a2d-118">Required.</span></span> <span data-ttu-id="46a2d-119">Nome locale del nodo discendente.</span><span class="sxs-lookup"><span data-stu-id="46a2d-119">Local name of the descendant node.</span></span> <span data-ttu-id="46a2d-120">Visualizzare [nomi degli elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="46a2d-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="46a2d-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="46a2d-121">Required.</span></span> <span data-ttu-id="46a2d-122">Indica la fine di una proprietà axis discendente.</span><span class="sxs-lookup"><span data-stu-id="46a2d-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46a2d-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="46a2d-123">Return Value</span></span>  
 <span data-ttu-id="46a2d-124">Raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="46a2d-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46a2d-125">Note</span><span class="sxs-lookup"><span data-stu-id="46a2d-125">Remarks</span></span>  
 <span data-ttu-id="46a2d-126">È possibile usare una proprietà axis discendente XML per accedere ai nodi discendenti in base al nome da un <xref:System.Xml.Linq.XElement> oppure <xref:System.Xml.Linq.XDocument> oggetto, o da una raccolta di <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> oggetti.</span><span class="sxs-lookup"><span data-stu-id="46a2d-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="46a2d-127">Usare il codice XML `Value` proprietà per accedere al valore del primo nodo discendente della raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="46a2d-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="46a2d-128">Per altre informazioni, vedere [proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="46a2d-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="46a2d-129">Il compilatore Visual Basic converte le proprietà axis discendente in chiamate al <xref:System.Xml.Linq.XContainer.Descendants%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="46a2d-129">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="46a2d-130">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="46a2d-130">XML Namespaces</span></span>  
 <span data-ttu-id="46a2d-131">Il nome di una proprietà axis discendente può usare solo spazi dei nomi XML dichiarati globalmente con il `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="46a2d-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="46a2d-132">Non può usare spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="46a2d-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="46a2d-133">Per altre informazioni, vedere [istruzione Imports (Namespace XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="46a2d-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46a2d-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="46a2d-134">Example</span></span>  
 <span data-ttu-id="46a2d-135">Nell'esempio seguente viene illustrato come accedere al valore del primo nodo discendente denominato `name` e i valori di tutti i nodi discendenti denominati `phone` dal `contacts` oggetto.</span><span class="sxs-lookup"><span data-stu-id="46a2d-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 <span data-ttu-id="46a2d-136">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="46a2d-136">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="46a2d-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="46a2d-137">Example</span></span>  
 <span data-ttu-id="46a2d-138">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="46a2d-138">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="46a2d-139">Il prefisso dello spazio dei nomi viene quindi utilizzato per creare un file XML letterale e accedere al valore del primo nodo figlio con il nome completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="46a2d-139">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 <span data-ttu-id="46a2d-140">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="46a2d-140">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="46a2d-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46a2d-141">See also</span></span>
- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="46a2d-142">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="46a2d-142">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="46a2d-143">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="46a2d-143">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="46a2d-144">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46a2d-144">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="46a2d-145">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="46a2d-145">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
