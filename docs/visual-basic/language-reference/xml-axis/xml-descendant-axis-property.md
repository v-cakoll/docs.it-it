---
title: "Proprietà axis descendant XML (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f3c42b5134b058c010ca4c7a5ee7c24627c65fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="d4821-102">Proprietà axis descendant XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4821-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="d4821-103">Fornisce l'accesso ai discendenti di uno dei seguenti: un <xref:System.Xml.Linq.XElement> oggetto, un <xref:System.Xml.Linq.XDocument> oggetto, una raccolta di <xref:System.Xml.Linq.XElement> oggetti o una raccolta di <xref:System.Xml.Linq.XDocument> oggetti.</span><span class="sxs-lookup"><span data-stu-id="d4821-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4821-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4821-104">Syntax</span></span>  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="d4821-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d4821-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="d4821-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d4821-106">Required.</span></span> <span data-ttu-id="d4821-107">Un oggetto <xref:System.Xml.Linq.XElement>, un oggetto <xref:System.Xml.Linq.XDocument>, una raccolta di oggetti <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="d4821-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="d4821-108">...<</span><span class="sxs-lookup"><span data-stu-id="d4821-108">...<</span></span>  
 <span data-ttu-id="d4821-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d4821-109">Required.</span></span> <span data-ttu-id="d4821-110">Indica l'inizio di una proprietà axis descendant.</span><span class="sxs-lookup"><span data-stu-id="d4821-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="d4821-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d4821-111">Required.</span></span> <span data-ttu-id="d4821-112">Nome dei nodi discendenti a cui accedere, nel formato [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="d4821-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="d4821-113">Parte</span><span class="sxs-lookup"><span data-stu-id="d4821-113">Part</span></span>|<span data-ttu-id="d4821-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4821-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="d4821-115">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d4821-115">Optional.</span></span> <span data-ttu-id="d4821-116">Prefisso dello spazio dei nomi XML per il nodo discendente.</span><span class="sxs-lookup"><span data-stu-id="d4821-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="d4821-117">Deve essere uno spazio dei nomi XML globale definito utilizzando un `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d4821-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="d4821-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d4821-118">Required.</span></span> <span data-ttu-id="d4821-119">Nome locale del nodo discendente.</span><span class="sxs-lookup"><span data-stu-id="d4821-119">Local name of the descendant node.</span></span> <span data-ttu-id="d4821-120">Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d4821-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="d4821-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d4821-121">Required.</span></span> <span data-ttu-id="d4821-122">Indica la fine di una proprietà axis descendant.</span><span class="sxs-lookup"><span data-stu-id="d4821-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4821-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d4821-123">Return Value</span></span>  
 <span data-ttu-id="d4821-124">Raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="d4821-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4821-125">Note</span><span class="sxs-lookup"><span data-stu-id="d4821-125">Remarks</span></span>  
 <span data-ttu-id="d4821-126">È possibile utilizzare una proprietà axis discendente XML per accedere a nodi discendenti in base al nome da un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> oggetto, o da una raccolta di <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> oggetti.</span><span class="sxs-lookup"><span data-stu-id="d4821-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="d4821-127">Utilizzare il codice XML `Value` proprietà per accedere al valore del primo nodo discendente nella raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="d4821-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="d4821-128">Per ulteriori informazioni, vedere [proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="d4821-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="d4821-129">Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore converte le proprietà axis descendant in chiamate al <xref:System.Xml.Linq.XContainer.Descendants%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="d4821-129">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="d4821-130">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="d4821-130">XML Namespaces</span></span>  
 <span data-ttu-id="d4821-131">Il nome in una proprietà axis descendant può utilizzare solo spazi dei nomi XML dichiarati globalmente con il `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d4821-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="d4821-132">È possibile utilizzare spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d4821-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="d4821-133">Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d4821-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4821-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4821-134">Example</span></span>  
 <span data-ttu-id="d4821-135">Nell'esempio seguente viene illustrato come accedere al valore del primo nodo discendente denominato `name` e i valori di tutti i nodi discendenti denominati `phone` dal `contacts` oggetto.</span><span class="sxs-lookup"><span data-stu-id="d4821-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 <span data-ttu-id="d4821-136">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="d4821-136">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="d4821-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4821-137">Example</span></span>  
 <span data-ttu-id="d4821-138">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="d4821-138">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="d4821-139">Viene quindi utilizzato il prefisso dello spazio dei nomi per creare valori letterali XML e accedere al valore del primo nodo figlio con il nome completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="d4821-139">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 <span data-ttu-id="d4821-140">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="d4821-140">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="d4821-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4821-141">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="d4821-142">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="d4821-142">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="d4821-143">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="d4821-143">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="d4821-144">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4821-144">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="d4821-145">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="d4821-145">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
