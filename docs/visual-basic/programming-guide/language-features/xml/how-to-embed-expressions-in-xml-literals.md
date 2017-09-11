---
title: 'Procedura: incorporare espressioni nei valori letterali XML (Visual Basic) | Documenti di Microsoft'
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
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
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
ms.openlocfilehash: e4f086b06575cb8300bd65d450cda6b9893bb692
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="1051c-102">Procedura: incorporare espressioni nei valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1051c-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="1051c-103">È possibile combinare i valori letterali XML con espressioni incorporate per creare un documento XML, frammento o elemento che contiene contenuto creato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1051c-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="1051c-104">Nell'esempio seguente viene illustrato come utilizzare le espressioni incorporate per popolare i nomi degli elementi, attributi e contenuto di un elemento in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1051c-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="1051c-105">La sintassi per un'espressione incorporata è `<%=` `exp` `%>`, che è la stessa sintassi che [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] utilizza.</span><span class="sxs-lookup"><span data-stu-id="1051c-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] uses.</span></span> <span data-ttu-id="1051c-106">Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1051c-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="1051c-107">È inoltre possibile utilizzare il [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API per creare [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] oggetti.</span><span class="sxs-lookup"><span data-stu-id="1051c-107">You can also use the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs to create [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects.</span></span> <span data-ttu-id="1051c-108">Per ulteriori informazioni, vedere <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1051c-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="1051c-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="1051c-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="1051c-110">Per inserire un testo come contenuto dell'elemento</span><span class="sxs-lookup"><span data-stu-id="1051c-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="1051c-111">Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `contactName` variabile tra gli elementi di nomi di apertura e chiusura.</span><span class="sxs-lookup"><span data-stu-id="1051c-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     <span data-ttu-id="1051c-112">[!code-vb[VbXMLSamples&#39;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1051c-112">[!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="1051c-113">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="1051c-113">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="1051c-114">Per inserire un testo come valore di attributo</span><span class="sxs-lookup"><span data-stu-id="1051c-114">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="1051c-115">Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `phoneType` come valore della variabile di `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="1051c-115">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     <span data-ttu-id="1051c-116">[!code-vb[&#40; VbXMLSamples](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="1051c-116">[!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="1051c-117">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="1051c-117">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="1051c-118">Per inserire del testo per un nome di elemento</span><span class="sxs-lookup"><span data-stu-id="1051c-118">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="1051c-119">Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `elementName` variabile come il nome di un elemento.</span><span class="sxs-lookup"><span data-stu-id="1051c-119">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="1051c-120">Quando si creano elementi utilizzando questa tecnica, è necessario chiudere con il \</ > tag.</span><span class="sxs-lookup"><span data-stu-id="1051c-120">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     <span data-ttu-id="1051c-121">[!code-vb[VbXMLSamples n.&41;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="1051c-121">[!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]</span></span>  
  
     <span data-ttu-id="1051c-122">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="1051c-122">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1051c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1051c-123">See Also</span></span>  
 <span data-ttu-id="1051c-124">[Procedura: creare valori letterali XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md) </span><span class="sxs-lookup"><span data-stu-id="1051c-124">[How to: Create XML Literals](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md) </span></span>  
<span data-ttu-id="1051c-125"> [Espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="1051c-125"> [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="1051c-126"> [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="1051c-126"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="1051c-127"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="1051c-127"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
