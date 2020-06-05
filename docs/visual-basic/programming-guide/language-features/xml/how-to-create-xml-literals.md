---
title: 'Procedura: creare valori letterali XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 61b138c0851c747ed30eedc10cb882cc3b03c4d4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392610"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="93773-102">Procedura: creare valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93773-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="93773-103">È possibile creare un documento, un frammento o un elemento XML direttamente nel codice usando un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="93773-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="93773-104">Negli esempi di questo argomento viene illustrato come creare un elemento XML con tre elementi figlio e come creare un documento XML.</span><span class="sxs-lookup"><span data-stu-id="93773-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="93773-105">È anche possibile usare le [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API per creare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti.</span><span class="sxs-lookup"><span data-stu-id="93773-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="93773-106">Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="93773-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="93773-107">Per creare un elemento XML</span><span class="sxs-lookup"><span data-stu-id="93773-107">To create an XML element</span></span>  
  
- <span data-ttu-id="93773-108">Creare l'XML inline usando la sintassi del valore letterale XML, che corrisponde alla sintassi XML effettiva.</span><span class="sxs-lookup"><span data-stu-id="93773-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="93773-109">Eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="93773-109">Run the code.</span></span> <span data-ttu-id="93773-110">L'output di questo codice è:</span><span class="sxs-lookup"><span data-stu-id="93773-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="93773-111">Per creare un documento XML</span><span class="sxs-lookup"><span data-stu-id="93773-111">To create an XML document</span></span>  
  
- <span data-ttu-id="93773-112">Creare il documento XML inline.</span><span class="sxs-lookup"><span data-stu-id="93773-112">Create the XML document inline.</span></span> <span data-ttu-id="93773-113">Il codice seguente crea un documento XML con sintassi letterale, una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="93773-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="93773-114">Eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="93773-114">Run the code.</span></span> <span data-ttu-id="93773-115">L'output di questo codice è:</span><span class="sxs-lookup"><span data-stu-id="93773-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="93773-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93773-116">See also</span></span>

- [<span data-ttu-id="93773-117">XML</span><span class="sxs-lookup"><span data-stu-id="93773-117">XML</span></span>](index.md)
- [<span data-ttu-id="93773-118">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93773-118">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="93773-119">Valore letterale di elemento XML</span><span class="sxs-lookup"><span data-stu-id="93773-119">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="93773-120">Valore letterale di documento XML</span><span class="sxs-lookup"><span data-stu-id="93773-120">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
