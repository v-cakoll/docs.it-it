---
title: Valore letterale di documento XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d5c84fecbb035c229cc3576bc556db6ecb6f3934
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="53f55-102">Valore letterale di documento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53f55-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="53f55-103">Un valore letterale che rappresenta un <xref:System.Xml.Linq.XDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="53f55-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f55-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53f55-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="53f55-105">Parti</span><span class="sxs-lookup"><span data-stu-id="53f55-105">Parts</span></span>  
  
|<span data-ttu-id="53f55-106">Termine</span><span class="sxs-lookup"><span data-stu-id="53f55-106">Term</span></span>|<span data-ttu-id="53f55-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="53f55-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="53f55-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="53f55-108">Optional.</span></span> <span data-ttu-id="53f55-109">Usa testo letterale che dichiara la codifica del documento.</span><span class="sxs-lookup"><span data-stu-id="53f55-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="53f55-110">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="53f55-110">Optional.</span></span> <span data-ttu-id="53f55-111">Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="53f55-111">Literal text.</span></span> <span data-ttu-id="53f55-112">Deve essere "yes" o "no".</span><span class="sxs-lookup"><span data-stu-id="53f55-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="53f55-113">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="53f55-113">Optional.</span></span> <span data-ttu-id="53f55-114">Elenco di istruzioni di elaborazione XML e commenti XML.</span><span class="sxs-lookup"><span data-stu-id="53f55-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="53f55-115">Assume il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="53f55-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="53f55-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="53f55-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="53f55-117">Ogni `piComment` può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="53f55-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="53f55-118">-   [Valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="53f55-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="53f55-119">-   [Valore letterale commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="53f55-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="53f55-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="53f55-120">Required.</span></span> <span data-ttu-id="53f55-121">Elemento radice del documento.</span><span class="sxs-lookup"><span data-stu-id="53f55-121">Root element of the document.</span></span> <span data-ttu-id="53f55-122">Il formato è uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="53f55-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="53f55-123">[Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="53f55-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="53f55-124">Espressione incorporata del formato `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="53f55-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="53f55-125">Il `elementExp` restituisce uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="53f55-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="53f55-126">Oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="53f55-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="53f55-127">Una raccolta che contiene uno <xref:System.Xml.Linq.XElement> oggetto e un numero qualsiasi di <xref:System.Xml.Linq.XProcessingInstruction> e <xref:System.Xml.Linq.XComment> oggetti.</span><span class="sxs-lookup"><span data-stu-id="53f55-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="53f55-128">Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="53f55-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="53f55-129">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="53f55-129">Return Value</span></span>  
 <span data-ttu-id="53f55-130">Oggetto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="53f55-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53f55-131">Note</span><span class="sxs-lookup"><span data-stu-id="53f55-131">Remarks</span></span>  
 <span data-ttu-id="53f55-132">Un valore letterale documento XML è identificato dalla dichiarazione XML all'inizio del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="53f55-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="53f55-133">Sebbene ogni valore letterale documento XML deve avere esattamente un elemento XML radice, può contenere un numero qualsiasi di istruzioni di elaborazione e commenti XML.</span><span class="sxs-lookup"><span data-stu-id="53f55-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="53f55-134">Un valore letterale documento XML non può trovarsi in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="53f55-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53f55-135">Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="53f55-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="53f55-136">In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="53f55-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="53f55-137">Il compilatore Visual Basic converte il valore letterale documento XML in chiamate per il <xref:System.Xml.Linq.XDocument.%23ctor%2A> e <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> costruttori.</span><span class="sxs-lookup"><span data-stu-id="53f55-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53f55-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="53f55-138">Example</span></span>  
 <span data-ttu-id="53f55-139">L'esempio seguente crea un documento XML con una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="53f55-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="53f55-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53f55-140">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 <xref:System.Xml.Linq.XComment>  
 <xref:System.Xml.Linq.XDocument>  
 [<span data-ttu-id="53f55-141">Valore letterale istruzione di elaborazione XML</span><span class="sxs-lookup"><span data-stu-id="53f55-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)  
 [<span data-ttu-id="53f55-142">Valore letterale di commento XML</span><span class="sxs-lookup"><span data-stu-id="53f55-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="53f55-143">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="53f55-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="53f55-144">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="53f55-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="53f55-145">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53f55-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="53f55-146">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="53f55-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
