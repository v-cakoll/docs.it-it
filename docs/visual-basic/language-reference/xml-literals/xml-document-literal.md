---
title: Valore letterale di documento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: 3a2182d2937827bc8dc45e22307a3668420261a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400202"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="0002f-102">Valore letterale di documento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0002f-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="0002f-103">Valore letterale che rappresenta un <xref:System.Xml.Linq.XDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="0002f-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0002f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0002f-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="0002f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0002f-105">Parts</span></span>  
  
|<span data-ttu-id="0002f-106">Termine</span><span class="sxs-lookup"><span data-stu-id="0002f-106">Term</span></span>|<span data-ttu-id="0002f-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="0002f-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="0002f-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0002f-108">Optional.</span></span> <span data-ttu-id="0002f-109">Testo letterale che dichiara la codifica utilizzata dal documento.</span><span class="sxs-lookup"><span data-stu-id="0002f-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="0002f-110">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0002f-110">Optional.</span></span> <span data-ttu-id="0002f-111">Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="0002f-111">Literal text.</span></span> <span data-ttu-id="0002f-112">Deve essere "Yes" o "No".</span><span class="sxs-lookup"><span data-stu-id="0002f-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="0002f-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0002f-113">Optional.</span></span> <span data-ttu-id="0002f-114">Elenco di istruzioni di elaborazione XML e commenti XML.</span><span class="sxs-lookup"><span data-stu-id="0002f-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="0002f-115">Accetta il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="0002f-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="0002f-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="0002f-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="0002f-117">Ognuno `piComment` può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0002f-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="0002f-118">-   [Valore letterale istruzione di elaborazione XML](xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="0002f-118">-   [XML Processing Instruction Literal](xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="0002f-119">-   [Valore letterale del commento XML](xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="0002f-119">-   [XML Comment Literal](xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="0002f-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0002f-120">Required.</span></span> <span data-ttu-id="0002f-121">Elemento radice del documento.</span><span class="sxs-lookup"><span data-stu-id="0002f-121">Root element of the document.</span></span> <span data-ttu-id="0002f-122">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0002f-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="0002f-123">[Valore letterale elemento XML](xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="0002f-123">[XML Element Literal](xml-element-literal.md).</span></span></li><li><span data-ttu-id="0002f-124">Espressione incorporata del form `<%=` `elementExp` `%>` .</span><span class="sxs-lookup"><span data-stu-id="0002f-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="0002f-125">`elementExp`Restituisce uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="0002f-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="0002f-126">Oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0002f-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="0002f-127">Raccolta che contiene un <xref:System.Xml.Linq.XElement> oggetto e un numero qualsiasi di <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment> oggetti e.</span><span class="sxs-lookup"><span data-stu-id="0002f-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="0002f-128">Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0002f-128">For more information, see [Embedded Expressions in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="0002f-129">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0002f-129">Return Value</span></span>  
 <span data-ttu-id="0002f-130">Oggetto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="0002f-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0002f-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="0002f-131">Remarks</span></span>  
 <span data-ttu-id="0002f-132">Un valore letterale di documento XML viene identificato dalla dichiarazione XML all'inizio del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="0002f-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="0002f-133">Sebbene ogni valore letterale del documento XML debba contenere esattamente un elemento XML radice, può includere un numero qualsiasi di istruzioni di elaborazione XML e commenti XML.</span><span class="sxs-lookup"><span data-stu-id="0002f-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="0002f-134">Un valore letterale di documento XML non può essere incluso in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="0002f-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0002f-135">Un valore letterale XML può estendersi su più righe senza usare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="0002f-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="0002f-136">In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0002f-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="0002f-137">Il compilatore Visual Basic converte il valore letterale del documento XML in chiamate ai <xref:System.Xml.Linq.XDocument.%23ctor%2A> <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> costruttori e.</span><span class="sxs-lookup"><span data-stu-id="0002f-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0002f-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="0002f-138">Example</span></span>  
 <span data-ttu-id="0002f-139">Nell'esempio seguente viene creato un documento XML con una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="0002f-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="0002f-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0002f-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="0002f-141">Valore letterale di istruzione di elaborazione XML</span><span class="sxs-lookup"><span data-stu-id="0002f-141">XML Processing Instruction Literal</span></span>](xml-processing-instruction-literal.md)
- [<span data-ttu-id="0002f-142">Valore letterale di commento XML</span><span class="sxs-lookup"><span data-stu-id="0002f-142">XML Comment Literal</span></span>](xml-comment-literal.md)
- [<span data-ttu-id="0002f-143">Valore letterale di elemento XML</span><span class="sxs-lookup"><span data-stu-id="0002f-143">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="0002f-144">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="0002f-144">XML Literals</span></span>](index.md)
- [<span data-ttu-id="0002f-145">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0002f-145">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="0002f-146">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="0002f-146">Embedded Expressions in XML</span></span>](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
