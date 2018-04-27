---
title: Spazi vuoti nei valori letterali XML (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6d23aa54b150748aac9aa955f4bd86ee88358ea
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="1b017-102">Spazi vuoti nei valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b017-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="1b017-103">Il compilatore Visual Basic incorpora solo i caratteri spazi vuoti significativi da un valore letterale XML durante la creazione di un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto.</span><span class="sxs-lookup"><span data-stu-id="1b017-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="1b017-104">I caratteri spazi vuoti non significativi non vengono incorporati.</span><span class="sxs-lookup"><span data-stu-id="1b017-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="1b017-105">Spazi vuoti significativi e non significativi</span><span class="sxs-lookup"><span data-stu-id="1b017-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="1b017-106">Gli spazi vuoti nei valori letterali XML sono significativi solo tre aree:</span><span class="sxs-lookup"><span data-stu-id="1b017-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="1b017-107">Quando si trovano in un valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="1b017-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="1b017-108">Quando fanno parte di un elemento contenuto di testo e il testo contiene anche altri caratteri.</span><span class="sxs-lookup"><span data-stu-id="1b017-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="1b017-109">Quando si trovano in un'espressione incorporata per il contenuto di testo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="1b017-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="1b017-110">In caso contrario, il compilatore considera gli spazi vuoti non significativi e non li include nel [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto per il valore letterale.</span><span class="sxs-lookup"><span data-stu-id="1b017-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="1b017-111">Per includere gli spazi vuoti in un valore letterale XML, utilizzare un'espressione incorporata che contiene una valore letterale stringa con lo spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="1b017-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b017-112">Se il `xml:space` viene visualizzato l'attributo in un valore letterale elemento XML, il compilatore Visual Basic include l'attributo nel <xref:System.Xml.Linq.XElement> oggetto, ma l'aggiunta di questo attributo non modifica il modo in cui il compilatore considera lo spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="1b017-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1b017-113">Esempi</span><span class="sxs-lookup"><span data-stu-id="1b017-113">Examples</span></span>  
 <span data-ttu-id="1b017-114">Nell'esempio seguente contiene due elementi XML esterni e interni.</span><span class="sxs-lookup"><span data-stu-id="1b017-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="1b017-115">Entrambi gli elementi contengono spazi vuoti nel contenuto di testo.</span><span class="sxs-lookup"><span data-stu-id="1b017-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="1b017-116">Lo spazio vuoto nell'elemento esterno è trascurabile perché contiene solo spazi vuoti e un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="1b017-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="1b017-117">Lo spazio vuoto nell'elemento interno è significativo perché contiene spazi vuoti e testo.</span><span class="sxs-lookup"><span data-stu-id="1b017-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 <span data-ttu-id="1b017-118">Durante l'esecuzione, questo codice visualizza il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="1b017-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b017-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b017-119">See Also</span></span>  
 [<span data-ttu-id="1b017-120">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b017-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
