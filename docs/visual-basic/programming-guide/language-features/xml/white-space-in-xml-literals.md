---
title: Spazi vuoti nei valori letterali XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 08be345557d10a528aa03234883eba1b3a31beaa
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832755"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Spazi vuoti nei valori letterali XML (Visual Basic)
Il compilatore Visual Basic include solo i caratteri spazi vuoti significativi da un valore letterale XML durante la creazione di un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto. I caratteri spazi vuoti non significativi non vengono incorporati.  
  
## <a name="significant-and-insignificant-white-space"></a>Spazi vuoti significativi e non significativi  
 I caratteri spazi vuoti nei valori letterali XML sono significativi solo tre aree:  
  
-   Quando si trovano in un valore di attributo.  
  
-   Quando fanno parte di un elemento contenuto di testo e il testo contiene anche altri caratteri.  
  
-   Quando si trovano in un'espressione incorporata per il contenuto di testo di un elemento.  
  
 In caso contrario, il compilatore vengono considerati spazi vuoti non significativi e non li include nel [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto per il valore letterale.  
  
 Per includere spazi vuoti non significativi in un valore letterale XML, usare un'espressione incorporata che contiene una valore letterale stringa con lo spazio vuoto.  
  
> [!NOTE]
>  Se il `xml:space` attributo incluso in un valore letterale elemento XML, il compilatore Visual Basic include l'attributo di <xref:System.Xml.Linq.XElement> oggetto, ma l'aggiunta di questo attributo non modifica il modo in cui il compilatore considera gli spazi vuoti.  
  
## <a name="examples"></a>Esempi  
 L'esempio seguente contiene due elementi XML, esterni e interni. Entrambi gli elementi contengono spazi vuoti nel contenuto di testo. Lo spazio vuoto nell'elemento esterno non è significativo perché contiene solo spazi vuoti e un elemento XML. Lo spazio vuoto dell'elemento interno è significativo perché contiene spazi vuoti e testo.  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 Quando eseguito, questo codice visualizza il testo seguente.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
