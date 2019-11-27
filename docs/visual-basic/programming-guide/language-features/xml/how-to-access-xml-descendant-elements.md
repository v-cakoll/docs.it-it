---
title: 'Procedura: accedere agli elementi discendenti XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 63a094c3c2b20736f0ef6589c76d53b7cc96b29a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332310"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Procedura: accedere agli elementi discendenti XML (Visual Basic)
In questo esempio viene illustrato come utilizzare una proprietà axis descendant per accedere a tutti gli elementi XML con un nome specificato e che sono contenuti in un elemento XML. In particolare, usa la proprietà `Value` per ottenere il valore del primo elemento nella raccolta restituito dalla proprietà Axis `name` descendant. La proprietà dell'asse discendente `name` ottiene tutti gli elementi denominati `name` contenuti nell'oggetto `contacts`. In questo esempio viene inoltre utilizzata la proprietà axis descendant `phone` per accedere a tutti i discendenti denominati `phone` contenuti nell'oggetto `contacts`.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [Proprietà axis descendant XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [Proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
