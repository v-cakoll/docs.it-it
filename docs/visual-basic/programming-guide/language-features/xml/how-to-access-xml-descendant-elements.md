---
title: 'Procedura: accedere agli elementi discendenti XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 6d41844b540631df96740ce56818c125cf85e928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Procedura: accedere agli elementi discendenti XML (Visual Basic)
In questo esempio viene illustrato come utilizzare una proprietà axis descendant per accedere a tutti gli elementi XML che hanno un nome specificato e che sono contenuti in un elemento XML. In particolare, viene utilizzata la `Value` proprietà per ottenere il valore del primo elemento nella raccolta la `name` restituisce proprietà axis descendant. Il `name` proprietà axis descendant Ottiene tutti gli elementi denominati `name` in esso contenute il `contacts` oggetto. Questo esempio Usa anche il `phone` proprietà axis descendant per accedere a tutti i discendenti denominati `phone` in esso contenute il `contacts` oggetto.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [Proprietà axis descendant XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [Proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [Accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
