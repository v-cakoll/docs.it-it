---
title: Valore letterale CDATA XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 01a505130d566ec88a6d87e5e9ad525e449d7298
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981244"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="2c6ee-102">Valore letterale CDATA XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c6ee-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="2c6ee-103">Un valore letterale che rappresenta un <xref:System.Xml.Linq.XCData> oggetto.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c6ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c6ee-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="2c6ee-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2c6ee-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="2c6ee-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-106">Required.</span></span> <span data-ttu-id="2c6ee-107">Indica l'inizio della sezione CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="2c6ee-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-108">Required.</span></span> <span data-ttu-id="2c6ee-109">Contenuto di testo da visualizzare nella sezione CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="2c6ee-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-110">Required.</span></span> <span data-ttu-id="2c6ee-111">Indica la fine della sezione.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c6ee-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2c6ee-112">Return Value</span></span>  
 <span data-ttu-id="2c6ee-113">Oggetto <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c6ee-114">Note</span><span class="sxs-lookup"><span data-stu-id="2c6ee-114">Remarks</span></span>  
 <span data-ttu-id="2c6ee-115">Le sezioni CDATA XML contengono testo non elaborato che deve essere inclusa, ma non analizzato, con il codice XML che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="2c6ee-116">Una sezione CDATA XML può contenere qualsiasi testo.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="2c6ee-117">Sono inclusi caratteri XML riservati.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-117">This includes reserved XML characters.</span></span> <span data-ttu-id="2c6ee-118">La sezione CDATA XML termina con la sequenza "]] >".</span><span class="sxs-lookup"><span data-stu-id="2c6ee-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="2c6ee-119">Ciò implica quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2c6ee-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="2c6ee-120">È possibile usare un'espressione incorporata in un valore letterale CDATA XML perché i delimitatori di espressioni incorporate sono contenuto CDATA XML valido.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="2c6ee-121">Le sezioni CDATA XML non possono essere annidate, perché `content` non può contenere il valore "]] >".</span><span class="sxs-lookup"><span data-stu-id="2c6ee-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="2c6ee-122">È possibile assegnare un valore letterale CDATA XML a una variabile o includerlo in un valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c6ee-123">Un valore letterale XML può estendersi su più righe ma non utilizza caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="2c6ee-124">In questo modo è possibile copiare il contenuto da un documento XML e incollare il codice direttamente in un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="2c6ee-125">Il compilatore Visual Basic consente di convertire il valore letterale CDATA XML a una chiamata al <xref:System.Xml.Linq.XCData.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="2c6ee-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c6ee-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c6ee-126">Example</span></span>  
 <span data-ttu-id="2c6ee-127">L'esempio seguente crea una sezione CDATA che contiene il testo "può contenere un valore letterale \<XML > tag".</span><span class="sxs-lookup"><span data-stu-id="2c6ee-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="2c6ee-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c6ee-128">See also</span></span>
- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="2c6ee-129">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="2c6ee-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="2c6ee-130">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="2c6ee-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="2c6ee-131">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c6ee-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
