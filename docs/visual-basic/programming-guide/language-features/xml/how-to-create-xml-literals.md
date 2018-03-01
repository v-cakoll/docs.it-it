---
title: 'Procedura: creare valori letterali XML (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce1bf763529b436158c2d74811c4938182166f92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="0c804-102">Procedura: creare valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c804-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="0c804-103">È possibile creare un documento XML, frammento o elemento direttamente nel codice utilizzando un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="0c804-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="0c804-104">Negli esempi in questo argomento viene illustrato come creare un elemento XML che dispone di tre elementi figlio e come creare un documento XML.</span><span class="sxs-lookup"><span data-stu-id="0c804-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="0c804-105">È inoltre possibile utilizzare il [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API per creare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti.</span><span class="sxs-lookup"><span data-stu-id="0c804-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="0c804-106">Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0c804-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="0c804-107">Per creare un elemento XML</span><span class="sxs-lookup"><span data-stu-id="0c804-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="0c804-108">Creare il XML inline utilizzando la sintassi del valore letterale XML, che corrisponde alla sintassi XML effettivo.</span><span class="sxs-lookup"><span data-stu-id="0c804-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     <span data-ttu-id="0c804-109">Eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="0c804-109">Run the code.</span></span> <span data-ttu-id="0c804-110">L'output di questo codice è:</span><span class="sxs-lookup"><span data-stu-id="0c804-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="0c804-111">Per creare un documento XML</span><span class="sxs-lookup"><span data-stu-id="0c804-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="0c804-112">Creare il documento XML inline.</span><span class="sxs-lookup"><span data-stu-id="0c804-112">Create the XML document inline.</span></span> <span data-ttu-id="0c804-113">Il codice seguente crea un documento XML con una sintassi del valore letterale, una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="0c804-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     <span data-ttu-id="0c804-114">Eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="0c804-114">Run the code.</span></span> <span data-ttu-id="0c804-115">L'output di questo codice è:</span><span class="sxs-lookup"><span data-stu-id="0c804-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="0c804-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c804-116">See Also</span></span>  
 [<span data-ttu-id="0c804-117">XML</span><span class="sxs-lookup"><span data-stu-id="0c804-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="0c804-118">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c804-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="0c804-119">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="0c804-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="0c804-120">Valore letterale di documento XML</span><span class="sxs-lookup"><span data-stu-id="0c804-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
