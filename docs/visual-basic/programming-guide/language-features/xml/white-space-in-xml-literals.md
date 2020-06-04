---
title: Spazi vuoti nei valori letterali XML
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: b3caf7ac052f3fed3fe5427da0cc96bbdd955ea6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360475"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="a2264-102">Spazi vuoti nei valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2264-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="a2264-103">Il compilatore Visual Basic incorpora solo gli spazi vuoti significativi da un valore letterale XML durante la creazione di un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto.</span><span class="sxs-lookup"><span data-stu-id="a2264-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="a2264-104">Gli spazi vuoti non significativi non sono incorporati.</span><span class="sxs-lookup"><span data-stu-id="a2264-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="a2264-105">Spazi vuoti significativi e non significativi</span><span class="sxs-lookup"><span data-stu-id="a2264-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="a2264-106">Gli spazi vuoti nei valori letterali XML sono significativi solo in tre aree:</span><span class="sxs-lookup"><span data-stu-id="a2264-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="a2264-107">Quando si trovano in un valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="a2264-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="a2264-108">Quando fanno parte del contenuto di testo di un elemento e il testo contiene anche altri caratteri.</span><span class="sxs-lookup"><span data-stu-id="a2264-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="a2264-109">Quando si trovano in un'espressione incorporata per il contenuto di testo di un elemento.</span><span class="sxs-lookup"><span data-stu-id="a2264-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="a2264-110">In caso contrario, il compilatore considera gli spazi vuoti come insignificanti e non include quindi nell' [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto per il valore letterale.</span><span class="sxs-lookup"><span data-stu-id="a2264-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="a2264-111">Per includere spazi vuoti non significativi in un valore letterale XML, utilizzare un'espressione incorporata contenente un valore letterale stringa con lo spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="a2264-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2264-112">Se l' `xml:space` attributo viene visualizzato in un valore letterale elemento XML, il compilatore Visual Basic include l'attributo nell' <xref:System.Xml.Linq.XElement> oggetto, ma l'aggiunta di questo attributo non modifica la modalità con cui il compilatore considera gli spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="a2264-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a2264-113">Esempi</span><span class="sxs-lookup"><span data-stu-id="a2264-113">Examples</span></span>  
 <span data-ttu-id="a2264-114">Nell'esempio seguente sono contenuti due elementi XML, outer e Inner.</span><span class="sxs-lookup"><span data-stu-id="a2264-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="a2264-115">Entrambi gli elementi contengono spazi vuoti nel contenuto di testo.</span><span class="sxs-lookup"><span data-stu-id="a2264-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="a2264-116">Gli spazi vuoti nell'elemento esterno non sono significativi perché contengono solo spazi vuoti e un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="a2264-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="a2264-117">Lo spazio vuoto nell'elemento interno è significativo perché contiene spazi vuoti e testo.</span><span class="sxs-lookup"><span data-stu-id="a2264-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="a2264-118">Quando viene eseguito, questo codice Visualizza il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="a2264-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2264-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2264-119">See also</span></span>

- [<span data-ttu-id="a2264-120">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a2264-120">Creating XML in Visual Basic</span></span>](creating-xml.md)
