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
# <a name="white-space-in-xml-literals-visual-basic"></a>Spazi vuoti nei valori letterali XML (Visual Basic)
Il compilatore Visual Basic incorpora solo gli spazi vuoti significativi da un valore letterale XML durante la creazione di un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto. Gli spazi vuoti non significativi non sono incorporati.  
  
## <a name="significant-and-insignificant-white-space"></a>Spazi vuoti significativi e non significativi  
 Gli spazi vuoti nei valori letterali XML sono significativi solo in tre aree:  
  
- Quando si trovano in un valore di attributo.  
  
- Quando fanno parte del contenuto di testo di un elemento e il testo contiene anche altri caratteri.  
  
- Quando si trovano in un'espressione incorporata per il contenuto di testo di un elemento.  
  
 In caso contrario, il compilatore considera gli spazi vuoti come insignificanti e non include quindi nell' [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto per il valore letterale.  
  
 Per includere spazi vuoti non significativi in un valore letterale XML, utilizzare un'espressione incorporata contenente un valore letterale stringa con lo spazio vuoto.  
  
> [!NOTE]
> Se l' `xml:space` attributo viene visualizzato in un valore letterale elemento XML, il compilatore Visual Basic include l'attributo nell' <xref:System.Xml.Linq.XElement> oggetto, ma l'aggiunta di questo attributo non modifica la modalità con cui il compilatore considera gli spazi vuoti.  
  
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

- [Creazione di XML in Visual Basic](creating-xml.md)
