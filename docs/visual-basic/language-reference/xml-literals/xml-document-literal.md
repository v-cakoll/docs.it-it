---
title: Valore letterale documento XML (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
dev_langs:
- VB
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
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
ms.openlocfilehash: 5e173c8bc89f61925c3e6127fb3cac61379aeffa
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="e4827-102">Valore letterale di documento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4827-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="e4827-103">Un valore letterale che rappresenta un <xref:System.Xml.Linq.XDocument>oggetto.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="e4827-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4827-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4827-104">Syntax</span></span>  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="e4827-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e4827-105">Parts</span></span>  
  
|<span data-ttu-id="e4827-106">Termine</span><span class="sxs-lookup"><span data-stu-id="e4827-106">Term</span></span>|<span data-ttu-id="e4827-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4827-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="e4827-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e4827-108">Optional.</span></span> <span data-ttu-id="e4827-109">Utilizza il testo letterale che dichiara la codifica del documento.</span><span class="sxs-lookup"><span data-stu-id="e4827-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="e4827-110">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e4827-110">Optional.</span></span> <span data-ttu-id="e4827-111">Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="e4827-111">Literal text.</span></span> <span data-ttu-id="e4827-112">Deve essere "yes" o "no".</span><span class="sxs-lookup"><span data-stu-id="e4827-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="e4827-113">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e4827-113">Optional.</span></span> <span data-ttu-id="e4827-114">Elenco di istruzioni di elaborazione e commenti XML.</span><span class="sxs-lookup"><span data-stu-id="e4827-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="e4827-115">Accetta il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="e4827-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="e4827-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="e4827-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="e4827-117">Ogni `piComment`può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4827-117">Each `piComment`can be one of the following:</span></span><br /><br /><span data-ttu-id="e4827-118"> -   [Valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e4827-118"> -   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="e4827-119">-   [Valore letterale commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e4827-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="e4827-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e4827-120">Required.</span></span> <span data-ttu-id="e4827-121">Elemento radice del documento.</span><span class="sxs-lookup"><span data-stu-id="e4827-121">Root element of the document.</span></span> <span data-ttu-id="e4827-122">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4827-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="e4827-123">[Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e4827-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="e4827-124">Espressione incorporata del formato `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="e4827-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="e4827-125">Il `elementExp` restituisce uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4827-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="e4827-126">Un <xref:System.Xml.Linq.XElement>oggetto.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e4827-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="e4827-127">Una raccolta che contiene un <xref:System.Xml.Linq.XElement>oggetto e un numero qualsiasi di <xref:System.Xml.Linq.XProcessingInstruction>e <xref:System.Xml.Linq.XComment>oggetti.</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e4827-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="e4827-128">Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e4827-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="e4827-129">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e4827-129">Return Value</span></span>  
 <span data-ttu-id="e4827-130">Un <xref:System.Xml.Linq.XDocument>oggetto.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="e4827-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4827-131">Note</span><span class="sxs-lookup"><span data-stu-id="e4827-131">Remarks</span></span>  
 <span data-ttu-id="e4827-132">Un valore letterale documento XML viene identificato dalla dichiarazione XML all'inizio del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="e4827-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="e4827-133">Sebbene ogni valore letterale documento XML deve avere esattamente un elemento XML radice, può contenere un numero qualsiasi di istruzioni di elaborazione e commenti XML.</span><span class="sxs-lookup"><span data-stu-id="e4827-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="e4827-134">Un valore letterale documento XML non può trovarsi in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="e4827-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4827-135">Un valore letterale XML può occupare più righe senza utilizzare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="e4827-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="e4827-136">Ciò consente di copiare il contenuto da un documento XML e incollarlo direttamente in un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programma.</span><span class="sxs-lookup"><span data-stu-id="e4827-136">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="e4827-137">Il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore converte il valore letterale documento XML in chiamate per il <xref:System.Xml.Linq.XDocument.%23ctor%2A>e <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>costruttori.</xref:System.Xml.Linq.XDeclaration.%23ctor%2A> </xref:System.Xml.Linq.XDocument.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="e4827-137">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4827-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="e4827-138">Example</span></span>  
 <span data-ttu-id="e4827-139">Nell'esempio seguente viene creato un documento XML che dispone di una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="e4827-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 <span data-ttu-id="e4827-140">[!code-vb[&#30; VbXMLSamples](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e4827-140">[!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4827-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4827-141">See Also</span></span>  
 <span data-ttu-id="e4827-142"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e4827-142"><xref:System.Xml.Linq.XElement></span></span>   
 <span data-ttu-id="e4827-143"><xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="e4827-143"><xref:System.Xml.Linq.XProcessingInstruction></span></span>   
 <span data-ttu-id="e4827-144"><xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="e4827-144"><xref:System.Xml.Linq.XComment></span></span>   
 <span data-ttu-id="e4827-145"><xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="e4827-145"><xref:System.Xml.Linq.XDocument></span></span>   
<span data-ttu-id="e4827-146"> [Valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e4827-146"> [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md) </span></span>  
<span data-ttu-id="e4827-147"> [Valore letterale commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e4827-147"> [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span></span>  
<span data-ttu-id="e4827-148"> [Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e4827-148"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="e4827-149"> [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4827-149"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="e4827-150"> [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e4827-150"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="e4827-151"> [Espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)</span><span class="sxs-lookup"><span data-stu-id="e4827-151"> [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)</span></span>
