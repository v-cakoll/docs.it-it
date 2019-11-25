---
title: Valore letterale di commento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 8d9db66aabe344bd5c8f9a92ac8618b7bc1abb43
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349392"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="8d727-102">Valore letterale di commento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d727-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="8d727-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span><span class="sxs-lookup"><span data-stu-id="8d727-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d727-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d727-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="8d727-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8d727-105">Parts</span></span>  
  
|<span data-ttu-id="8d727-106">Termine</span><span class="sxs-lookup"><span data-stu-id="8d727-106">Term</span></span>|<span data-ttu-id="8d727-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="8d727-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="8d727-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8d727-108">Required.</span></span> <span data-ttu-id="8d727-109">Denotes the start of the XML comment.</span><span class="sxs-lookup"><span data-stu-id="8d727-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="8d727-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8d727-110">Required.</span></span> <span data-ttu-id="8d727-111">Text to appear in the XML comment.</span><span class="sxs-lookup"><span data-stu-id="8d727-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="8d727-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span><span class="sxs-lookup"><span data-stu-id="8d727-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="8d727-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8d727-113">Required.</span></span> <span data-ttu-id="8d727-114">Denotes the end of the XML comment.</span><span class="sxs-lookup"><span data-stu-id="8d727-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="8d727-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8d727-115">Return Value</span></span>  
 <span data-ttu-id="8d727-116">Oggetto <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="8d727-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d727-117">Note</span><span class="sxs-lookup"><span data-stu-id="8d727-117">Remarks</span></span>  
 <span data-ttu-id="8d727-118">XML comment literals do not contain document content; they contain information about the document.</span><span class="sxs-lookup"><span data-stu-id="8d727-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="8d727-119">The XML comment section ends with the sequence "-->".</span><span class="sxs-lookup"><span data-stu-id="8d727-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="8d727-120">This implies the following points:</span><span class="sxs-lookup"><span data-stu-id="8d727-120">This implies the following points:</span></span>  
  
- <span data-ttu-id="8d727-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span><span class="sxs-lookup"><span data-stu-id="8d727-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
- <span data-ttu-id="8d727-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span><span class="sxs-lookup"><span data-stu-id="8d727-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="8d727-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span><span class="sxs-lookup"><span data-stu-id="8d727-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d727-124">An XML literal can span multiple lines without using line continuation characters.</span><span class="sxs-lookup"><span data-stu-id="8d727-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="8d727-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span><span class="sxs-lookup"><span data-stu-id="8d727-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="8d727-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="8d727-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d727-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d727-127">Example</span></span>  
 <span data-ttu-id="8d727-128">The following example creates an XML comment that contains the text "This is a comment".</span><span class="sxs-lookup"><span data-stu-id="8d727-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="8d727-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d727-129">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="8d727-130">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="8d727-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="8d727-131">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="8d727-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="8d727-132">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8d727-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
