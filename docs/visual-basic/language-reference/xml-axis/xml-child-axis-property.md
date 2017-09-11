---
title: "Proprietà di asse figlio XML (Visual Basic) | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyChildAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
caps.latest.revision: 18
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
ms.openlocfilehash: 2ccdacdadf219b9c928558f07e0890be6471d40a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="d552b-102">Proprietà Child Axis XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d552b-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="d552b-103">Fornisce l'accesso agli elementi figlio di uno dei seguenti: un <xref:System.Xml.Linq.XElement>oggetto, un <xref:System.Xml.Linq.XDocument>oggetto, una raccolta di <xref:System.Xml.Linq.XElement>oggetti o una raccolta di <xref:System.Xml.Linq.XDocument>oggetti.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d552b-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d552b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d552b-104">Syntax</span></span>  
  
```  
  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="d552b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d552b-105">Parts</span></span>  
  
|<span data-ttu-id="d552b-106">Termine</span><span class="sxs-lookup"><span data-stu-id="d552b-106">Term</span></span>|<span data-ttu-id="d552b-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="d552b-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="d552b-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d552b-108">Required.</span></span> <span data-ttu-id="d552b-109">Un <xref:System.Xml.Linq.XElement>oggetto, un <xref:System.Xml.Linq.XDocument>oggetto, una raccolta di <xref:System.Xml.Linq.XElement>oggetti o una raccolta di <xref:System.Xml.Linq.XDocument>oggetti.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d552b-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="d552b-110">.<</span><span class="sxs-lookup"><span data-stu-id="d552b-110">.<</span></span>|<span data-ttu-id="d552b-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d552b-111">Required.</span></span> <span data-ttu-id="d552b-112">Indica l'inizio di una proprietà axis dell'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="d552b-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="d552b-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d552b-113">Required.</span></span> <span data-ttu-id="d552b-114">Nome dei nodi figlio a cui accedere, nel formato [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="d552b-114">Name of the child nodes to access, of the form [`prefix``:`]`name`.</span></span><br /><br /><span data-ttu-id="d552b-115"> -   `Prefix`-Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d552b-115"> -   `Prefix` - Optional.</span></span> <span data-ttu-id="d552b-116">Prefisso dello spazio dei nomi XML per il nodo figlio.</span><span class="sxs-lookup"><span data-stu-id="d552b-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="d552b-117">Deve essere uno spazio dei nomi XML globale definito usando un'istruzione `Imports`.</span><span class="sxs-lookup"><span data-stu-id="d552b-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="d552b-118">-   `Name`-Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d552b-118">-   `Name` - Required.</span></span> <span data-ttu-id="d552b-119">Nome del nodo figlio locale.</span><span class="sxs-lookup"><span data-stu-id="d552b-119">Local child node name.</span></span> <span data-ttu-id="d552b-120">Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d552b-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="d552b-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d552b-121">Required.</span></span> <span data-ttu-id="d552b-122">Indica la fine di una proprietà axis dell'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="d552b-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="d552b-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d552b-123">Return Value</span></span>  
 <span data-ttu-id="d552b-124">Una raccolta di <xref:System.Xml.Linq.XElement>oggetti.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d552b-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d552b-125">Note</span><span class="sxs-lookup"><span data-stu-id="d552b-125">Remarks</span></span>  
 <span data-ttu-id="d552b-126">È possibile utilizzare una proprietà child axis XML per accedere a nodi figlio in base al nome da un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>oggetto, o da una raccolta di <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>oggetti.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d552b-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="d552b-127">Usare la proprietà `Value` XML per accedere al valore del primo nodo figlio nella raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="d552b-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="d552b-128">Per ulteriori informazioni, vedere [proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="d552b-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="d552b-129">Il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore converte le proprietà axis figlio per le chiamate al <xref:System.Xml.Linq.XContainer.Elements%2A>(metodo).</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="d552b-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="d552b-130">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="d552b-130">XML Namespaces</span></span>  
 <span data-ttu-id="d552b-131">Il nome in una proprietà axis dell'elemento figlio può usare solo prefissi degli spazi dei nomi XML dichiarati globalmente con l'istruzione `Imports`.</span><span class="sxs-lookup"><span data-stu-id="d552b-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="d552b-132">Non può usare prefissi degli spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d552b-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="d552b-133">Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d552b-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d552b-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="d552b-134">Example</span></span>  
 <span data-ttu-id="d552b-135">L'esempio seguente illustra come accedere ai nodi figlio denominati `phone` dall'oggetto `contact`.</span><span class="sxs-lookup"><span data-stu-id="d552b-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 <span data-ttu-id="d552b-136">[!code-vb[VbXMLSamples n.&17;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d552b-136">[!code-vb[VbXMLSamples#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="d552b-137">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="d552b-137">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="d552b-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="d552b-138">Example</span></span>  
 <span data-ttu-id="d552b-139">L'esempio seguente illustra come accedere ai nodi figlio denominati `phone` dalla raccolta restituita dalla proprietà axis dell'elemento figlio `contact` dell'oggetto `contacts`.</span><span class="sxs-lookup"><span data-stu-id="d552b-139">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 <span data-ttu-id="d552b-140">[!code-vb[VbXMLSamples&#18;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="d552b-140">[!code-vb[VbXMLSamples#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="d552b-141">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="d552b-141">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="d552b-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="d552b-142">Example</span></span>  
 <span data-ttu-id="d552b-143">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="d552b-143">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="d552b-144">Il prefisso dello spazio dei nomi viene quindi usato per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="d552b-144">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 <span data-ttu-id="d552b-145">[!code-vb[&#19; VbXMLSamples](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="d552b-145">[!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]</span></span>  
  
 <span data-ttu-id="d552b-146">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="d552b-146">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="d552b-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d552b-147">See Also</span></span>  
 <span data-ttu-id="d552b-148"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d552b-148"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="d552b-149"> [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="d552b-149"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="d552b-150"> [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="d552b-150"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="d552b-151"> [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="d552b-151"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="d552b-152"> [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="d552b-152"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
