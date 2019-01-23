---
title: Valore letterale di commento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 96a7281cde546c3077cf15c625c6e09d2d0ee46f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624678"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="b0c5f-102">Valore letterale di commento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0c5f-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="b0c5f-103">Un valore letterale che rappresenta un <xref:System.Xml.Linq.XComment> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c5f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0c5f-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="b0c5f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b0c5f-105">Parts</span></span>  
  
|<span data-ttu-id="b0c5f-106">Termine</span><span class="sxs-lookup"><span data-stu-id="b0c5f-106">Term</span></span>|<span data-ttu-id="b0c5f-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="b0c5f-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="b0c5f-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-108">Required.</span></span> <span data-ttu-id="b0c5f-109">Indica l'inizio del commento XML.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="b0c5f-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-110">Required.</span></span> <span data-ttu-id="b0c5f-111">Testo da inserire nel commento XML.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="b0c5f-112">Non può contenere una serie di due trattini (-) o terminare con un trattino adiacente al tag di chiusura.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="b0c5f-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-113">Required.</span></span> <span data-ttu-id="b0c5f-114">Indica la fine del commento XML.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="b0c5f-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b0c5f-115">Return Value</span></span>  
 <span data-ttu-id="b0c5f-116">Oggetto <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0c5f-117">Note</span><span class="sxs-lookup"><span data-stu-id="b0c5f-117">Remarks</span></span>  
 <span data-ttu-id="b0c5f-118">Valori letterali di commento XML non contengono il contenuto del documento; contengono informazioni relative al documento.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="b0c5f-119">Sezione dei commenti XML termina con la sequenza "-->".</span><span class="sxs-lookup"><span data-stu-id="b0c5f-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="b0c5f-120">Ciò implica quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0c5f-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="b0c5f-121">È possibile usare un'espressione incorporata in un valore letterale del commento XML perché i delimitatori di espressioni incorporate sono contenuti di commento XML validi.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="b0c5f-122">Le sezioni di commento XML non possono essere nidificate, poiché `content` non può contenere il valore "-->".</span><span class="sxs-lookup"><span data-stu-id="b0c5f-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="b0c5f-123">È possibile assegnare un valore letterale del commento XML a una variabile, oppure è possibile includerlo in un valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0c5f-124">Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="b0c5f-125">Questa funzionalità consente di copiare il contenuto da un documento XML e incollare il codice direttamente in un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="b0c5f-126">Il compilatore Visual Basic converte il valore letterale del commento XML in una chiamata al <xref:System.Xml.Linq.XComment.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="b0c5f-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0c5f-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0c5f-127">Example</span></span>  
 <span data-ttu-id="b0c5f-128">L'esempio seguente crea un commento XML che contiene il testo "This is a un commento".</span><span class="sxs-lookup"><span data-stu-id="b0c5f-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b0c5f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0c5f-129">See also</span></span>
- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="b0c5f-130">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="b0c5f-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="b0c5f-131">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="b0c5f-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="b0c5f-132">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b0c5f-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
