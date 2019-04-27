---
title: Valore letterale di documento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: f58c1365e145166dfe122d455854d44526300a1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799307"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="83a79-102">Valore letterale di documento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83a79-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="83a79-103">Un valore letterale che rappresenta un <xref:System.Xml.Linq.XDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="83a79-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83a79-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="83a79-105">Parti</span><span class="sxs-lookup"><span data-stu-id="83a79-105">Parts</span></span>  
  
|<span data-ttu-id="83a79-106">Termine</span><span class="sxs-lookup"><span data-stu-id="83a79-106">Term</span></span>|<span data-ttu-id="83a79-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="83a79-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="83a79-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="83a79-108">Optional.</span></span> <span data-ttu-id="83a79-109">Usa testo letterale che dichiara la codifica del documento.</span><span class="sxs-lookup"><span data-stu-id="83a79-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="83a79-110">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="83a79-110">Optional.</span></span> <span data-ttu-id="83a79-111">Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="83a79-111">Literal text.</span></span> <span data-ttu-id="83a79-112">Deve essere "yes" o "no".</span><span class="sxs-lookup"><span data-stu-id="83a79-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="83a79-113">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="83a79-113">Optional.</span></span> <span data-ttu-id="83a79-114">Elenco di istruzioni di elaborazione XML e commenti in formato XML.</span><span class="sxs-lookup"><span data-stu-id="83a79-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="83a79-115">Assume il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="83a79-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="83a79-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="83a79-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="83a79-117">Ogni `piComment` può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="83a79-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="83a79-118">-   [Valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="83a79-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="83a79-119">-   [Valore letterale commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="83a79-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="83a79-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="83a79-120">Required.</span></span> <span data-ttu-id="83a79-121">Elemento radice del documento.</span><span class="sxs-lookup"><span data-stu-id="83a79-121">Root element of the document.</span></span> <span data-ttu-id="83a79-122">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="83a79-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="83a79-123">[Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="83a79-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="83a79-124">Espressione del form incorporata `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="83a79-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="83a79-125">Il `elementExp` restituisce uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="83a79-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="83a79-126">Oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="83a79-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="83a79-127">Una raccolta che contiene un <xref:System.Xml.Linq.XElement> oggetto e un numero qualsiasi di <xref:System.Xml.Linq.XProcessingInstruction> e <xref:System.Xml.Linq.XComment> oggetti.</span><span class="sxs-lookup"><span data-stu-id="83a79-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="83a79-128">Per altre informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="83a79-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="83a79-129">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="83a79-129">Return Value</span></span>  
 <span data-ttu-id="83a79-130">Oggetto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="83a79-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83a79-131">Note</span><span class="sxs-lookup"><span data-stu-id="83a79-131">Remarks</span></span>  
 <span data-ttu-id="83a79-132">Un valore letterale documento XML viene identificato dalla dichiarazione XML all'inizio del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="83a79-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="83a79-133">Anche se ogni valore letterale documento XML deve avere esattamente un elemento XML radice, può avere un numero qualsiasi di istruzioni di elaborazione XML e commenti in formato XML.</span><span class="sxs-lookup"><span data-stu-id="83a79-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="83a79-134">Un valore letterale documento XML non può trovarsi in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="83a79-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83a79-135">Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="83a79-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="83a79-136">In questo modo è possibile copiare il contenuto da un documento XML e incollare il codice direttamente in un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="83a79-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="83a79-137">Il compilatore Visual Basic converte il valore letterale documento XML in chiamate per il <xref:System.Xml.Linq.XDocument.%23ctor%2A> e <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> costruttori.</span><span class="sxs-lookup"><span data-stu-id="83a79-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83a79-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="83a79-138">Example</span></span>  
 <span data-ttu-id="83a79-139">L'esempio seguente crea un documento XML che dispone di una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="83a79-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="83a79-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83a79-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="83a79-141">Valore letterale istruzione di elaborazione XML</span><span class="sxs-lookup"><span data-stu-id="83a79-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="83a79-142">Valore letterale di commento XML</span><span class="sxs-lookup"><span data-stu-id="83a79-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="83a79-143">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="83a79-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="83a79-144">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="83a79-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="83a79-145">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83a79-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="83a79-146">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="83a79-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
