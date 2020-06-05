---
title: 'Procedura: accedere agli elementi figlio XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 994249801eecc2984947efac9712df0047f076a4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392818"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Procedura: accedere agli elementi figlio XML (Visual Basic)
Questo esempio illustra come usare una proprietà Axis figlio per accedere a tutti gli elementi figlio XML con un nome specificato in un elemento XML. In particolare, usa la <xref:System.Xml.Linq.XElement.Value%2A> proprietà per ottenere il valore del primo elemento nella raccolta `name` restituita dalla proprietà dell'asse figlio. La `name` Proprietà Axis figlio ottiene tutti gli elementi figlio denominati `phone` nell' `contact` oggetto. In questo esempio viene inoltre utilizzata la `phone` Proprietà Axis figlio per accedere a tutti gli elementi figlio denominati `phone` contenuti nell' `contact` oggetto.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a>Compilare il codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [XML Child Axis Property](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [Proprietà Value XML](../../../language-reference/xml-axis/xml-value-property.md)
- [Accesso a XML in Visual Basic](accessing-xml.md)
- [XML](index.md)
