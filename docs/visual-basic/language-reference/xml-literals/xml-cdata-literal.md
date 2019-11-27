---
title: Valore letterale CDATA XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 72e899e7bd30f2edf0e88207bb3b75bdf36fa11c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349430"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="62a2f-102">Valore letterale CDATA XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62a2f-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="62a2f-103">Valore letterale che rappresenta un oggetto <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="62a2f-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62a2f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62a2f-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="62a2f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="62a2f-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="62a2f-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="62a2f-106">Required.</span></span> <span data-ttu-id="62a2f-107">Indica l'inizio della sezione CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="62a2f-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="62a2f-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="62a2f-108">Required.</span></span> <span data-ttu-id="62a2f-109">Contenuto di testo da visualizzare nella sezione CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="62a2f-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="62a2f-110">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="62a2f-110">Required.</span></span> <span data-ttu-id="62a2f-111">Indica la fine della sezione.</span><span class="sxs-lookup"><span data-stu-id="62a2f-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62a2f-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="62a2f-112">Return Value</span></span>  
 <span data-ttu-id="62a2f-113">Oggetto <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="62a2f-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62a2f-114">Note</span><span class="sxs-lookup"><span data-stu-id="62a2f-114">Remarks</span></span>  
 <span data-ttu-id="62a2f-115">Le sezioni CDATA XML contengono testo non elaborato che deve essere incluso, ma non analizzato, con il codice XML che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="62a2f-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="62a2f-116">Una sezione CDATA XML può contenere testo.</span><span class="sxs-lookup"><span data-stu-id="62a2f-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="62a2f-117">Sono inclusi i caratteri XML riservati.</span><span class="sxs-lookup"><span data-stu-id="62a2f-117">This includes reserved XML characters.</span></span> <span data-ttu-id="62a2f-118">La sezione CDATA XML termina con la sequenza "]] >".</span><span class="sxs-lookup"><span data-stu-id="62a2f-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="62a2f-119">Questo implica i seguenti punti:</span><span class="sxs-lookup"><span data-stu-id="62a2f-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="62a2f-120">Non è possibile usare un'espressione incorporata in un valore letterale CDATA XML perché i delimitatori di espressioni incorporati sono contenuti CDATA XML validi.</span><span class="sxs-lookup"><span data-stu-id="62a2f-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="62a2f-121">Le sezioni CDATA XML non possono essere annidate, perché `content` non può contenere il valore "]] >".</span><span class="sxs-lookup"><span data-stu-id="62a2f-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="62a2f-122">È possibile assegnare un valore letterale CDATA XML a una variabile o includerlo in un valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="62a2f-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62a2f-123">Un valore letterale XML può estendersi su più righe, ma non utilizza caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="62a2f-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="62a2f-124">In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="62a2f-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="62a2f-125">Il compilatore Visual Basic converte il valore letterale CDATA XML in una chiamata al costruttore di <xref:System.Xml.Linq.XCData.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="62a2f-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62a2f-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="62a2f-126">Example</span></span>  
 <span data-ttu-id="62a2f-127">Nell'esempio seguente viene creata una sezione CDATA che contiene il testo "può contenere un valore letterale \<tag XML >".</span><span class="sxs-lookup"><span data-stu-id="62a2f-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="62a2f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62a2f-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="62a2f-129">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="62a2f-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="62a2f-130">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="62a2f-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="62a2f-131">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62a2f-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
