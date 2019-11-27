---
title: Spazi vuoti nei valori letterali XML
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 56ededeb12d07e979bc86b03924e1ae0f0432822
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336001"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Spazi vuoti nei valori letterali XML (Visual Basic)
Il compilatore Visual Basic incorpora solo gli spazi vuoti significativi da un valore letterale XML quando crea un oggetto [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Gli spazi vuoti non significativi non sono incorporati.  
  
## <a name="significant-and-insignificant-white-space"></a>Spazi vuoti significativi e non significativi  
 Gli spazi vuoti nei valori letterali XML sono significativi solo in tre aree:  
  
- Quando si trovano in un valore di attributo.  
  
- Quando fanno parte del contenuto di testo di un elemento e il testo contiene anche altri caratteri.  
  
- Quando si trovano in un'espressione incorporata per il contenuto di testo di un elemento.  
  
 In caso contrario, il compilatore considera gli spazi vuoti come insignificanti e non include quindi nell'oggetto [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per il valore letterale.  
  
 Per includere spazi vuoti non significativi in un valore letterale XML, utilizzare un'espressione incorporata contenente un valore letterale stringa con lo spazio vuoto.  
  
> [!NOTE]
> Se l'attributo `xml:space` viene visualizzato in un valore letterale elemento XML, il compilatore Visual Basic include l'attributo nell'oggetto <xref:System.Xml.Linq.XElement>, ma l'aggiunta di questo attributo non modifica la modalità con cui il compilatore considera gli spazi vuoti.  
  
## <a name="examples"></a>Esempi  
 Nell'esempio seguente sono contenuti due elementi XML, outer e Inner. Entrambi gli elementi contengono spazi vuoti nel contenuto di testo. Gli spazi vuoti nell'elemento esterno non sono significativi perché contengono solo spazi vuoti e un elemento XML. Lo spazio vuoto nell'elemento interno è significativo perché contiene spazi vuoti e testo.  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 Quando viene eseguito, questo codice Visualizza il testo seguente.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
