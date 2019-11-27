---
title: 'Procedura: accedere agli elementi figlio XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: af5ea809cb0777b16230f20e133764dd5f1f86d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332333"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Procedura: accedere agli elementi figlio XML (Visual Basic)
Questo esempio illustra come usare una proprietà Axis figlio per accedere a tutti gli elementi figlio XML con un nome specificato in un elemento XML. In particolare, usa la proprietà <xref:System.Xml.Linq.XElement.Value%2A> per ottenere il valore del primo elemento nella raccolta restituita dalla proprietà dell'asse figlio `name`. La proprietà dell'asse figlio `name` ottiene tutti gli elementi figlio denominati `phone` nell'oggetto `contact`. Questo esempio usa anche la proprietà `phone` AXIS Child per accedere a tutti gli elementi figlio denominati `phone` contenuti nell'oggetto `contact`.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [Proprietà Child Axis XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
