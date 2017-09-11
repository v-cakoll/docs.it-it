---
title: "Proprietà Axis Descendant XML (Visual Basic) | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyDescendantsAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e84a8bb989ebbed57595ebf93cef620027a04328
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="80b37-102">Proprietà axis descendant XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80b37-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="80b37-103">Fornisce l'accesso ai discendenti di uno dei seguenti: un <xref:System.Xml.Linq.XElement>oggetto, un <xref:System.Xml.Linq.XDocument>oggetto, una raccolta di <xref:System.Xml.Linq.XElement>oggetti o una raccolta di <xref:System.Xml.Linq.XDocument>oggetti.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="80b37-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80b37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80b37-104">Syntax</span></span>  
  
```  
  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="80b37-105">Parti</span><span class="sxs-lookup"><span data-stu-id="80b37-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="80b37-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="80b37-106">Required.</span></span> <span data-ttu-id="80b37-107">Un <xref:System.Xml.Linq.XElement>oggetto, un <xref:System.Xml.Linq.XDocument>oggetto, una raccolta di <xref:System.Xml.Linq.XElement>oggetti o una raccolta di <xref:System.Xml.Linq.XDocument>oggetti.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="80b37-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="80b37-108">...<</span><span class="sxs-lookup"><span data-stu-id="80b37-108">...<</span></span>  
 <span data-ttu-id="80b37-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="80b37-109">Required.</span></span> <span data-ttu-id="80b37-110">Indica l'inizio di una proprietà axis descendant.</span><span class="sxs-lookup"><span data-stu-id="80b37-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="80b37-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="80b37-111">Required.</span></span> <span data-ttu-id="80b37-112">Nome dei nodi discendente per accedere, nel formato [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="80b37-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="80b37-113">Parte</span><span class="sxs-lookup"><span data-stu-id="80b37-113">Part</span></span>|<span data-ttu-id="80b37-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80b37-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="80b37-115">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="80b37-115">Optional.</span></span> <span data-ttu-id="80b37-116">Prefisso dello spazio dei nomi XML per il nodo discendente.</span><span class="sxs-lookup"><span data-stu-id="80b37-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="80b37-117">Deve essere uno spazio dei nomi XML globale viene definito mediante un `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="80b37-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="80b37-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="80b37-118">Required.</span></span> <span data-ttu-id="80b37-119">Nome locale del nodo discendente.</span><span class="sxs-lookup"><span data-stu-id="80b37-119">Local name of the descendant node.</span></span> <span data-ttu-id="80b37-120">Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="80b37-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="80b37-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="80b37-121">Required.</span></span> <span data-ttu-id="80b37-122">Indica la fine di una proprietà axis descendant.</span><span class="sxs-lookup"><span data-stu-id="80b37-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80b37-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="80b37-123">Return Value</span></span>  
 <span data-ttu-id="80b37-124">Una raccolta di <xref:System.Xml.Linq.XElement>oggetti.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="80b37-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80b37-125">Note</span><span class="sxs-lookup"><span data-stu-id="80b37-125">Remarks</span></span>  
 <span data-ttu-id="80b37-126">È possibile utilizzare una proprietà axis descendant XML per accedere a nodi discendenti in base al nome da un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>oggetto, o da una raccolta di <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>oggetti.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="80b37-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="80b37-127">Utilizzare il codice XML `Value` proprietà per accedere al valore del primo nodo discendente nella raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="80b37-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="80b37-128">Per ulteriori informazioni, vedere [proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="80b37-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="80b37-129">Il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore converte le proprietà axis descendant in chiamate per il <xref:System.Xml.Linq.XContainer.Descendants%2A>(metodo).</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="80b37-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="80b37-130">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="80b37-130">XML Namespaces</span></span>  
 <span data-ttu-id="80b37-131">Il nome di una proprietà axis descendant può utilizzare solo spazi dei nomi XML dichiarati globalmente con il `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="80b37-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="80b37-132">È possibile utilizzare gli spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="80b37-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="80b37-133">Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="80b37-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="80b37-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="80b37-134">Example</span></span>  
 <span data-ttu-id="80b37-135">Nell'esempio seguente viene illustrato come accedere al valore del primo nodo discendente denominato `name` e i valori di tutti i nodi discendenti denominati `phone` dal `contacts` oggetto.</span><span class="sxs-lookup"><span data-stu-id="80b37-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 <span data-ttu-id="80b37-136">[!code-vb[VbXMLSamples&#25;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="80b37-136">[!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="80b37-137">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="80b37-137">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="80b37-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="80b37-138">Example</span></span>  
 <span data-ttu-id="80b37-139">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="80b37-139">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="80b37-140">Viene quindi utilizzato il prefisso dello spazio dei nomi per creare valori letterali XML e accedere al valore del primo nodo figlio con il nome completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="80b37-140">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 <span data-ttu-id="80b37-141">[!code-vb[&#26; VbXMLSamples](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="80b37-141">[!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="80b37-142">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="80b37-142">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="80b37-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80b37-143">See Also</span></span>  
 <span data-ttu-id="80b37-144"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="80b37-144"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="80b37-145"> [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="80b37-145"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="80b37-146"> [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="80b37-146"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="80b37-147"> [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="80b37-147"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="80b37-148"> [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="80b37-148"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
