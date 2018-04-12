---
title: Valore letterale istruzione di elaborazione XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9ce0f2d0dff80072beefdb4f84643ea28e2cf165
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="3fa83-102">Valore letterale istruzione di elaborazione XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fa83-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="3fa83-103">Un valore letterale che rappresenta un <xref:System.Xml.Linq.XProcessingInstruction> oggetto.</span><span class="sxs-lookup"><span data-stu-id="3fa83-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fa83-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fa83-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="3fa83-105">Parti</span><span class="sxs-lookup"><span data-stu-id="3fa83-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="3fa83-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3fa83-106">Required.</span></span> <span data-ttu-id="3fa83-107">Indica l'inizio dell'istruzione di elaborazione XML letterale.</span><span class="sxs-lookup"><span data-stu-id="3fa83-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="3fa83-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3fa83-108">Required.</span></span> <span data-ttu-id="3fa83-109">Assegnare un nome che indica l'applicazione le destinazioni di istruzione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3fa83-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="3fa83-110">Non può iniziare con "xml" o "XML".</span><span class="sxs-lookup"><span data-stu-id="3fa83-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="3fa83-111">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3fa83-111">Optional.</span></span> <span data-ttu-id="3fa83-112">Stringa che indica come l'applicazione di destinazione da `piName` deve elaborare il documento XML.</span><span class="sxs-lookup"><span data-stu-id="3fa83-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="3fa83-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3fa83-113">Required.</span></span> <span data-ttu-id="3fa83-114">Indica la fine dell'istruzione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3fa83-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fa83-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3fa83-115">Return Value</span></span>  
 <span data-ttu-id="3fa83-116">Oggetto <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="3fa83-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fa83-117">Note</span><span class="sxs-lookup"><span data-stu-id="3fa83-117">Remarks</span></span>  
 <span data-ttu-id="3fa83-118">Valori letterali di istruzione di elaborazione XML indicano quali applicazioni devono elaborare un documento XML.</span><span class="sxs-lookup"><span data-stu-id="3fa83-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="3fa83-119">Quando un'applicazione viene caricato un documento XML, l'applicazione può controllare le istruzioni di elaborazione per determinare come elaborare il documento XML.</span><span class="sxs-lookup"><span data-stu-id="3fa83-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="3fa83-120">L'applicazione interpreta il significato di `piName` e `piData`.</span><span class="sxs-lookup"><span data-stu-id="3fa83-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="3fa83-121">Il valore letterale documento XML utilizza una sintassi simile a quello dell'istruzione di elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="3fa83-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="3fa83-122">Per ulteriori informazioni, vedere [valore letterale di documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="3fa83-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fa83-123">Il `piName` elemento non può iniziare con le stringhe "xml" o "XML", perché la specifica XML 1.0 tali identificatori sono riservati.</span><span class="sxs-lookup"><span data-stu-id="3fa83-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="3fa83-124">È possibile assegnare una valore letterale istruzione di elaborazione di XML a una variabile o includerlo in un valore letterale documento XML.</span><span class="sxs-lookup"><span data-stu-id="3fa83-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fa83-125">Un valore letterale XML può estendersi su più righe senza caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="3fa83-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="3fa83-126">Ciò consente di copiare il contenuto da un documento XML e incollarlo direttamente in un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programma.</span><span class="sxs-lookup"><span data-stu-id="3fa83-126">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="3fa83-127">Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore converte il valore letterale istruzione di elaborazione di XML a una chiamata al <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="3fa83-127">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fa83-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="3fa83-128">Example</span></span>  
 <span data-ttu-id="3fa83-129">L'esempio seguente crea un'istruzione di elaborazione che identifica un foglio di stile per un documento XML.</span><span class="sxs-lookup"><span data-stu-id="3fa83-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3fa83-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fa83-130">See Also</span></span>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [<span data-ttu-id="3fa83-131">Valore letterale di documento XML</span><span class="sxs-lookup"><span data-stu-id="3fa83-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [<span data-ttu-id="3fa83-132">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="3fa83-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="3fa83-133">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3fa83-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
