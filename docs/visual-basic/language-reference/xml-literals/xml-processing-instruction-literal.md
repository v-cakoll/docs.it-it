---
title: Valore letterale istruzione di elaborazione XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3602a81feae9287a77d060bb46f10eefee4fc05d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347040"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="fd7ee-102">Valore letterale istruzione di elaborazione XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd7ee-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="fd7ee-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd7ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd7ee-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="fd7ee-105">Parti</span><span class="sxs-lookup"><span data-stu-id="fd7ee-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="fd7ee-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-106">Required.</span></span> <span data-ttu-id="fd7ee-107">Denotes the start of the XML processing instruction literal.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="fd7ee-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-108">Required.</span></span> <span data-ttu-id="fd7ee-109">Name indicating which application the processing instruction targets.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="fd7ee-110">Cannot begin with "xml" or "XML".</span><span class="sxs-lookup"><span data-stu-id="fd7ee-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="fd7ee-111">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-111">Optional.</span></span> <span data-ttu-id="fd7ee-112">String indicating how the application targeted by `piName` should process the XML document.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="fd7ee-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-113">Required.</span></span> <span data-ttu-id="fd7ee-114">Denotes the end of the processing instruction.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd7ee-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fd7ee-115">Return Value</span></span>  
 <span data-ttu-id="fd7ee-116">Oggetto <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd7ee-117">Note</span><span class="sxs-lookup"><span data-stu-id="fd7ee-117">Remarks</span></span>  
 <span data-ttu-id="fd7ee-118">XML processing instruction literals indicate how applications should process an XML document.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="fd7ee-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="fd7ee-120">The application interprets the meaning of `piName` and `piData`.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="fd7ee-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="fd7ee-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="fd7ee-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd7ee-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="fd7ee-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd7ee-125">An XML literal can span multiple lines without needing line continuation characters.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="fd7ee-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="fd7ee-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd7ee-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd7ee-128">Example</span></span>  
 <span data-ttu-id="fd7ee-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span><span class="sxs-lookup"><span data-stu-id="fd7ee-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="fd7ee-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd7ee-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="fd7ee-131">Valore letterale di documento XML</span><span class="sxs-lookup"><span data-stu-id="fd7ee-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="fd7ee-132">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="fd7ee-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="fd7ee-133">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fd7ee-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
