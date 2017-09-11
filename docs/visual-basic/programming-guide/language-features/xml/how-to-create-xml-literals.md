---
title: 'Procedura: creare valori letterali XML (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: 17
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
ms.openlocfilehash: 3a7b5dc692317067290b48222ba056d765a449f3
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="e51f7-102">Procedura: creare valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e51f7-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="e51f7-103">È possibile creare un documento XML, frammento o elemento direttamente nel codice utilizzando un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="e51f7-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="e51f7-104">Negli esempi in questo argomento viene illustrato come creare un elemento XML che dispone di tre elementi figlio e come creare un documento XML.</span><span class="sxs-lookup"><span data-stu-id="e51f7-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="e51f7-105">È inoltre possibile utilizzare il [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API per creare [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] oggetti.</span><span class="sxs-lookup"><span data-stu-id="e51f7-105">You can also use the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs to create [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects.</span></span> <span data-ttu-id="e51f7-106">Per ulteriori informazioni, vedere <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e51f7-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="e51f7-107">Per creare un elemento XML</span><span class="sxs-lookup"><span data-stu-id="e51f7-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="e51f7-108">Creare il XML inline utilizzando la sintassi del valore letterale XML, che corrisponde all'effettiva sintassi XML.</span><span class="sxs-lookup"><span data-stu-id="e51f7-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     <span data-ttu-id="e51f7-109">[!code-vb[VbXMLSamples n.&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e51f7-109">[!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="e51f7-110">Eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="e51f7-110">Run the code.</span></span> <span data-ttu-id="e51f7-111">L'output di questo codice è:</span><span class="sxs-lookup"><span data-stu-id="e51f7-111">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="e51f7-112">Per creare un documento XML</span><span class="sxs-lookup"><span data-stu-id="e51f7-112">To create an XML document</span></span>  
  
-   <span data-ttu-id="e51f7-113">Creare il documento XML inline.</span><span class="sxs-lookup"><span data-stu-id="e51f7-113">Create the XML document inline.</span></span> <span data-ttu-id="e51f7-114">Il codice seguente crea un documento XML con la sintassi letterale, una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="e51f7-114">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     <span data-ttu-id="e51f7-115">[!code-vb[&#30; VbXMLSamples](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e51f7-115">[!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="e51f7-116">Eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="e51f7-116">Run the code.</span></span> <span data-ttu-id="e51f7-117">L'output di questo codice è:</span><span class="sxs-lookup"><span data-stu-id="e51f7-117">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="e51f7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e51f7-118">See Also</span></span>  
 <span data-ttu-id="e51f7-119">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="e51f7-119">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="e51f7-120"> [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e51f7-120"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="e51f7-121"> [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e51f7-121"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="e51f7-122"> [Valore letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)</span><span class="sxs-lookup"><span data-stu-id="e51f7-122"> [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)</span></span>
