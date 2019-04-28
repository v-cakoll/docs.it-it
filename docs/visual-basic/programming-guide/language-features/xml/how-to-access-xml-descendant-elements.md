---
title: 'Procedura: Accesso agli elementi discendenti XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: bfbf849bd296f639f03580346e4a9c52ce000abd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934810"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Procedura: Accesso agli elementi discendenti XML (Visual Basic)
In questo esempio viene illustrato come usare una proprietà axis discendente per accedere a tutti gli elementi XML con un nome specificato e che sono contenuti in un elemento XML. In particolare, viene utilizzata la `Value` proprietà da ottenere il valore del primo elemento nella raccolta che il `name` restituisce proprietà axis discendente. Il `name` proprietà axis descendant Ottiene tutti gli elementi denominati `name` contenuti nel `contacts` oggetto. Questo esempio Usa anche il `phone` proprietà axis discendente per accedere a tutti i discendenti denominati `phone` contenuti nel `contacts` oggetto.  
  
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
