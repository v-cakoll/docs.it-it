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
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="9fe8c-102">Valore letterale CDATA XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fe8c-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="9fe8c-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe8c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9fe8c-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="9fe8c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9fe8c-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="9fe8c-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-106">Required.</span></span> <span data-ttu-id="9fe8c-107">Denotes the start of the XML CDATA section.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="9fe8c-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-108">Required.</span></span> <span data-ttu-id="9fe8c-109">Text content to appear in the XML CDATA section.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="9fe8c-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-110">Required.</span></span> <span data-ttu-id="9fe8c-111">Denotes the end of the section.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fe8c-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9fe8c-112">Return Value</span></span>  
 <span data-ttu-id="9fe8c-113">Oggetto <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fe8c-114">Note</span><span class="sxs-lookup"><span data-stu-id="9fe8c-114">Remarks</span></span>  
 <span data-ttu-id="9fe8c-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="9fe8c-116">A XML CDATA section can contain any text.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="9fe8c-117">This includes reserved XML characters.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-117">This includes reserved XML characters.</span></span> <span data-ttu-id="9fe8c-118">The XML CDATA section ends with the sequence "]]>".</span><span class="sxs-lookup"><span data-stu-id="9fe8c-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="9fe8c-119">This implies the following points:</span><span class="sxs-lookup"><span data-stu-id="9fe8c-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="9fe8c-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="9fe8c-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span><span class="sxs-lookup"><span data-stu-id="9fe8c-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="9fe8c-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fe8c-123">An XML literal can span multiple lines but does not use line continuation characters.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="9fe8c-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="9fe8c-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="9fe8c-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fe8c-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="9fe8c-126">Example</span></span>  
 <span data-ttu-id="9fe8c-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span><span class="sxs-lookup"><span data-stu-id="9fe8c-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="9fe8c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fe8c-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="9fe8c-129">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="9fe8c-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="9fe8c-130">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="9fe8c-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="9fe8c-131">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9fe8c-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
