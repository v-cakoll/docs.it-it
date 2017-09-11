---
title: Spazi vuoti nei valori letterali XML (Visual Basic) | Documenti di Microsoft
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
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
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
ms.openlocfilehash: 4fc3d30a9c71cbd732597c5e3f32bd01eb489a80
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="9604a-102">Spazi vuoti nei valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9604a-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="9604a-103">Il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore incorpora solo i caratteri spazio vuoto significativo da un valore letterale XML quando viene creato un [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] oggetto.</span><span class="sxs-lookup"><span data-stu-id="9604a-103">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] object.</span></span> <span data-ttu-id="9604a-104">I caratteri spazi vuoti non significativi non vengono incorporati.</span><span class="sxs-lookup"><span data-stu-id="9604a-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="9604a-105">Spazi vuoti significativi e non significativi</span><span class="sxs-lookup"><span data-stu-id="9604a-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="9604a-106">Gli spazi vuoti nei valori letterali XML sono significativi solo tre aree:</span><span class="sxs-lookup"><span data-stu-id="9604a-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="9604a-107">Quando si trovano in un valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="9604a-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="9604a-108">Quando fanno parte dell'elemento contenuto di testo e il testo contiene anche altri caratteri.</span><span class="sxs-lookup"><span data-stu-id="9604a-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="9604a-109">Quando si trovano in un'espressione incorporata per il contenuto di testo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="9604a-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="9604a-110">In caso contrario, il compilatore considera gli spazi vuoti non significativi e non li include nel [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] oggetto per il valore letterale.</span><span class="sxs-lookup"><span data-stu-id="9604a-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="9604a-111">Per includere spazi vuoti non significativi in un valore letterale XML, utilizzare un'espressione incorporata che contiene una stringa letterale con lo spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="9604a-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9604a-112">Se il `xml:space` attributo viene visualizzato in un elemento XML letterale, il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore include l'attributo di <xref:System.Xml.Linq.XElement>oggetto, ma l'aggiunta di questo attributo non modifica il modo in cui il compilatore considera gli spazi vuoti.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="9604a-112">If the `xml:space` attribute appears in an XML element literal, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9604a-113">Esempi</span><span class="sxs-lookup"><span data-stu-id="9604a-113">Examples</span></span>  
 <span data-ttu-id="9604a-114">Nell'esempio seguente contiene due elementi XML, esterni e interni.</span><span class="sxs-lookup"><span data-stu-id="9604a-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="9604a-115">Entrambi gli elementi contengono spazi vuoti nel contenuto di testo.</span><span class="sxs-lookup"><span data-stu-id="9604a-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="9604a-116">Lo spazio vuoto nell'elemento esterno non è significativo perché contiene solo spazi vuoti e un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="9604a-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="9604a-117">Lo spazio vuoto nell'elemento interno è significativo perché contiene spazi vuoti e testo.</span><span class="sxs-lookup"><span data-stu-id="9604a-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 <span data-ttu-id="9604a-118">[!code-vb[VbXMLSamples&#29;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9604a-118">[!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]</span></span>  
  
 <span data-ttu-id="9604a-119">Durante l'esecuzione, questo codice viene visualizzato il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="9604a-119">When run, this code displays the following text.</span></span>  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9604a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9604a-120">See Also</span></span>  
 [<span data-ttu-id="9604a-121">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9604a-121">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
