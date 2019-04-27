---
title: 'Procedura: Incorporare espressioni nei valori letterali XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 31e79a8787978ffab2e35cd2827b80a8f1ed843e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61861361"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="60c5a-102">Procedura: Incorporare espressioni nei valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60c5a-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="60c5a-103">È possibile combinare i valori letterali XML con espressioni incorporate per creare un documento XML, frammento o elemento che contiene contenuto creato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="60c5a-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="60c5a-104">Gli esempi seguenti illustrano come usare espressioni incorporate per popolare i nomi degli elementi, attributi e contenuto di un elemento in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="60c5a-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="60c5a-105">Sintassi dell'espressione incorporata `<%=` `exp` `%>`, che è la stessa sintassi che [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] Usa.</span><span class="sxs-lookup"><span data-stu-id="60c5a-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="60c5a-106">Per altre informazioni, vedere [espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="60c5a-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="60c5a-107">È anche possibile usare la [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API per creare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti.</span><span class="sxs-lookup"><span data-stu-id="60c5a-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="60c5a-108">Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="60c5a-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="60c5a-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="60c5a-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="60c5a-110">Per inserire il testo come contenuto dell'elemento</span><span class="sxs-lookup"><span data-stu-id="60c5a-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="60c5a-111">Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `contactName` variabile tra gli elementi di nomi di apertura e chiusura.</span><span class="sxs-lookup"><span data-stu-id="60c5a-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="60c5a-112">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="60c5a-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="60c5a-113">Per inserire il testo come valore di attributo</span><span class="sxs-lookup"><span data-stu-id="60c5a-113">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="60c5a-114">Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `phoneType` variabile come valore del `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="60c5a-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="60c5a-115">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="60c5a-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="60c5a-116">Per inserire il testo per un nome di elemento</span><span class="sxs-lookup"><span data-stu-id="60c5a-116">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="60c5a-117">Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `elementName` variabile come nome di un elemento.</span><span class="sxs-lookup"><span data-stu-id="60c5a-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="60c5a-118">Quando si creano elementi utilizzando questa tecnica, è necessario chiuderli con la \</ > tag.</span><span class="sxs-lookup"><span data-stu-id="60c5a-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="60c5a-119">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="60c5a-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="60c5a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60c5a-120">See also</span></span>

- [<span data-ttu-id="60c5a-121">Procedura: Creare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="60c5a-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [<span data-ttu-id="60c5a-122">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="60c5a-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="60c5a-123">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60c5a-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="60c5a-124">XML</span><span class="sxs-lookup"><span data-stu-id="60c5a-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
