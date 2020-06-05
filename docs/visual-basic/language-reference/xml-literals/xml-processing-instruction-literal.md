---
title: Valore letterale di istruzione di elaborazione XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 9bd1781e01bc4cbf1ce5da8c454ab2f5a679aead
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400176"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="f2186-102">Valore letterale istruzione di elaborazione XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2186-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="f2186-103">Valore letterale che rappresenta un <xref:System.Xml.Linq.XProcessingInstruction> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f2186-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2186-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2186-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="f2186-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f2186-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="f2186-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f2186-106">Required.</span></span> <span data-ttu-id="f2186-107">Indica l'inizio del valore letterale di istruzione di elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="f2186-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="f2186-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f2186-108">Required.</span></span> <span data-ttu-id="f2186-109">Nome che indica l'applicazione di destinazione dell'istruzione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f2186-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="f2186-110">Impossibile iniziare con "XML" o "XML".</span><span class="sxs-lookup"><span data-stu-id="f2186-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="f2186-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f2186-111">Optional.</span></span> <span data-ttu-id="f2186-112">Stringa che indica il modo in cui l'applicazione di destinazione `piName` deve elaborare il documento XML.</span><span class="sxs-lookup"><span data-stu-id="f2186-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="f2186-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f2186-113">Required.</span></span> <span data-ttu-id="f2186-114">Indica la fine dell'istruzione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f2186-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2186-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f2186-115">Return Value</span></span>  
 <span data-ttu-id="f2186-116">Oggetto <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="f2186-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2186-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="f2186-117">Remarks</span></span>  
 <span data-ttu-id="f2186-118">I valori letterali di istruzione di elaborazione XML indicano in che modo le applicazioni devono elaborare un documento XML.</span><span class="sxs-lookup"><span data-stu-id="f2186-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="f2186-119">Quando un'applicazione carica un documento XML, l'applicazione è in grado di controllare le istruzioni di elaborazione XML per determinare la modalità di elaborazione del documento.</span><span class="sxs-lookup"><span data-stu-id="f2186-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="f2186-120">L'applicazione interpreta il significato di `piName` e `piData` .</span><span class="sxs-lookup"><span data-stu-id="f2186-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="f2186-121">Il valore letterale del documento XML utilizza una sintassi simile a quella dell'istruzione di elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="f2186-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="f2186-122">Per altre informazioni, vedere [valore letterale documento XML](xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f2186-122">For more information, see [XML Document Literal](xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2186-123">L' `piName` elemento non può iniziare con le stringhe "XML" o "XML", perché la specifica xml 1,0 riserva tali identificatori.</span><span class="sxs-lookup"><span data-stu-id="f2186-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="f2186-124">È possibile assegnare un valore letterale di istruzione di elaborazione XML a una variabile o includerlo in un valore letterale di documento XML.</span><span class="sxs-lookup"><span data-stu-id="f2186-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2186-125">Un valore letterale XML può estendersi su più righe senza dover utilizzare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="f2186-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="f2186-126">In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f2186-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="f2186-127">Il compilatore Visual Basic converte il valore letterale di istruzione di elaborazione XML in una chiamata al <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="f2186-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2186-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2186-128">Example</span></span>  
 <span data-ttu-id="f2186-129">Nell'esempio seguente viene creata un'istruzione di elaborazione che identifica un foglio di stile per un documento XML.</span><span class="sxs-lookup"><span data-stu-id="f2186-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="f2186-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2186-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="f2186-131">Valore letterale di documento XML</span><span class="sxs-lookup"><span data-stu-id="f2186-131">XML Document Literal</span></span>](xml-document-literal.md)
- [<span data-ttu-id="f2186-132">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="f2186-132">XML Literals</span></span>](index.md)
- [<span data-ttu-id="f2186-133">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f2186-133">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
