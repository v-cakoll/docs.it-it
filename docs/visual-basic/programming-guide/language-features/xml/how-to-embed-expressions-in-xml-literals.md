---
title: 'Procedura: incorporare espressioni nei valori letterali XML'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 59ba03be6e132203523427d3b7af5a163b6f05ac
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392314"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="ab531-102">Procedura: incorporare espressioni nei valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab531-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="ab531-103">È possibile combinare valori letterali XML con espressioni incorporate per creare un documento, un frammento o un elemento XML che contiene contenuto creato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ab531-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="ab531-104">Gli esempi seguenti illustrano come usare le espressioni incorporate per popolare il contenuto dell'elemento, gli attributi e i nomi degli elementi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ab531-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="ab531-105">La sintassi per un'espressione incorporata è `<%=` `exp` `%>` , ovvero la stessa sintassi utilizzata da ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ab531-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that ASP.NET uses.</span></span> <span data-ttu-id="ab531-106">Per ulteriori informazioni, vedere [espressioni incorporate in XML](embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ab531-106">For more information, see [Embedded Expressions in XML](embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="ab531-107">È anche possibile usare le [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API per creare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti.</span><span class="sxs-lookup"><span data-stu-id="ab531-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="ab531-108">Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ab531-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="ab531-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="ab531-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="ab531-110">Per inserire il testo come contenuto dell'elemento</span><span class="sxs-lookup"><span data-stu-id="ab531-110">To insert text as element content</span></span>  
  
- <span data-ttu-id="ab531-111">Nell'esempio seguente viene illustrato come inserire il testo contenuto nella `contactName` variabile tra gli elementi del nome di apertura e di chiusura.</span><span class="sxs-lookup"><span data-stu-id="ab531-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="ab531-112">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="ab531-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="ab531-113">Per inserire il testo come valore di attributo</span><span class="sxs-lookup"><span data-stu-id="ab531-113">To insert text as an attribute value</span></span>  
  
- <span data-ttu-id="ab531-114">Nell'esempio seguente viene illustrato come inserire il testo contenuto nella `phoneType` variabile come valore dell' `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="ab531-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="ab531-115">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="ab531-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="ab531-116">Per inserire il testo per il nome di un elemento</span><span class="sxs-lookup"><span data-stu-id="ab531-116">To insert text for an element name</span></span>  
  
- <span data-ttu-id="ab531-117">Nell'esempio seguente viene illustrato come inserire il testo contenuto nella `elementName` variabile come nome di un elemento.</span><span class="sxs-lookup"><span data-stu-id="ab531-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="ab531-118">Quando si creano elementi usando questa tecnica, è necessario chiuderli con il \</> tag.</span><span class="sxs-lookup"><span data-stu-id="ab531-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="ab531-119">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="ab531-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ab531-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab531-120">See also</span></span>

- [<span data-ttu-id="ab531-121">Procedura: Creare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="ab531-121">How to: Create XML Literals</span></span>](how-to-create-xml-literals.md)
- [<span data-ttu-id="ab531-122">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="ab531-122">Embedded Expressions in XML</span></span>](embedded-expressions-in-xml.md)
- [<span data-ttu-id="ab531-123">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab531-123">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="ab531-124">XML</span><span class="sxs-lookup"><span data-stu-id="ab531-124">XML</span></span>](index.md)
