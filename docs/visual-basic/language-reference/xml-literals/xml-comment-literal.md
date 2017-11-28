---
title: Valore letterale di commento XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36be34ac22cfe926a2eea946f5e4c4eb534de696
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="358bb-102">Valore letterale di commento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="358bb-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="358bb-103">Un valore letterale che rappresenta un <xref:System.Xml.Linq.XComment> oggetto.</span><span class="sxs-lookup"><span data-stu-id="358bb-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="358bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="358bb-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="358bb-105">Parti</span><span class="sxs-lookup"><span data-stu-id="358bb-105">Parts</span></span>  
  
|<span data-ttu-id="358bb-106">Termine</span><span class="sxs-lookup"><span data-stu-id="358bb-106">Term</span></span>|<span data-ttu-id="358bb-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="358bb-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="358bb-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="358bb-108">Required.</span></span> <span data-ttu-id="358bb-109">Indica l'inizio del commento XML.</span><span class="sxs-lookup"><span data-stu-id="358bb-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="358bb-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="358bb-110">Required.</span></span> <span data-ttu-id="358bb-111">Testo da visualizzare nel commento XML.</span><span class="sxs-lookup"><span data-stu-id="358bb-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="358bb-112">Non può contenere una serie di due trattini (-) o terminare con un trattino adiacente al tag di chiusura.</span><span class="sxs-lookup"><span data-stu-id="358bb-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="358bb-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="358bb-113">Required.</span></span> <span data-ttu-id="358bb-114">Indica la fine del commento XML.</span><span class="sxs-lookup"><span data-stu-id="358bb-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="358bb-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="358bb-115">Return Value</span></span>  
 <span data-ttu-id="358bb-116">Oggetto <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="358bb-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="358bb-117">Note</span><span class="sxs-lookup"><span data-stu-id="358bb-117">Remarks</span></span>  
 <span data-ttu-id="358bb-118">Valori letterali di commento XML non contengono il contenuto del documento; contengono informazioni sul documento.</span><span class="sxs-lookup"><span data-stu-id="358bb-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="358bb-119">La sezione di commento XML termina con la sequenza "-->".</span><span class="sxs-lookup"><span data-stu-id="358bb-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="358bb-120">Ciò implica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="358bb-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="358bb-121">È possibile utilizzare un'espressione incorporata in un valore letterale di commento XML perché i delimitatori di espressione incorporata sono contenuti di commento XML validi.</span><span class="sxs-lookup"><span data-stu-id="358bb-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="358bb-122">Le sezioni di commento XML non possono essere annidate, perché `content` non può contenere il valore "-->".</span><span class="sxs-lookup"><span data-stu-id="358bb-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="358bb-123">È possibile assegnare un valore letterale del commento XML a una variabile oppure è possibile includerlo in un valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="358bb-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="358bb-124">Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="358bb-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="358bb-125">Questa funzionalità consente di copiare il contenuto da un documento XML e incollarlo direttamente in un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programma.</span><span class="sxs-lookup"><span data-stu-id="358bb-125">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="358bb-126">Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore converte il valore letterale del commento XML a una chiamata al <xref:System.Xml.Linq.XComment.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="358bb-126">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="358bb-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="358bb-127">Example</span></span>  
 <span data-ttu-id="358bb-128">L'esempio seguente crea un commento XML che contiene il testo "This is a un commento".</span><span class="sxs-lookup"><span data-stu-id="358bb-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="358bb-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="358bb-129">See Also</span></span>  
 <xref:System.Xml.Linq.XComment>  
 [<span data-ttu-id="358bb-130">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="358bb-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="358bb-131">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="358bb-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="358bb-132">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="358bb-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
