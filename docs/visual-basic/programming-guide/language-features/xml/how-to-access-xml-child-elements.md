---
title: 'Procedura: accedere agli elementi figlio XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 4ec7743a30b8101d813ac414a8f5164aeb6c593d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649204"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Procedura: accedere agli elementi figlio XML (Visual Basic)
In questo esempio viene illustrato come utilizzare un elemento figlio di proprietà dell'asse di accesso a tutti gli elementi figlio XML che hanno un nome specificato in un elemento XML. In particolare, viene utilizzata la <xref:System.Xml.Linq.XElement.Value%2A> proprietà per ottenere il valore del primo elemento nella raccolta il `name` restituisce proprietà di asse figlio. Il `name` proprietà child axis Ottiene tutti gli elementi figlio denominati `phone` nel `contact` oggetto. Questo esempio Usa anche il `phone` proprietà child axis per accedere a tutti gli elementi figlio denominati `phone` in esso contenute il `contact` oggetto.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbXMLSamples#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-child-elements_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
 [Proprietà Child Axis XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [Proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [Accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
