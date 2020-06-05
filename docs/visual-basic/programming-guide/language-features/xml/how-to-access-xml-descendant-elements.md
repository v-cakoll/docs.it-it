---
title: 'Procedura: accedere agli elementi discendenti XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 03c403aa3c187b0b9d2006104eccaa1f9cd8aec5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392636"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Procedura: accedere agli elementi discendenti XML (Visual Basic)
In questo esempio viene illustrato come utilizzare una proprietà axis descendant per accedere a tutti gli elementi XML con un nome specificato e che sono contenuti in un elemento XML. In particolare, usa la `Value` proprietà per ottenere il valore del primo elemento nella raccolta `name` restituita dalla proprietà dell'asse discendente. La `name` proprietà dell'asse discendente ottiene tutti gli elementi denominati `name` contenuti nell' `contacts` oggetto. In questo esempio viene inoltre utilizzata la `phone` proprietà axis descendant per accedere a tutti i discendenti denominati `phone` contenuti nell' `contacts` oggetto.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a>Compilare il codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [XML Descendant Axis Property](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [Proprietà Value XML](../../../language-reference/xml-axis/xml-value-property.md)
- [Accesso a XML in Visual Basic](accessing-xml.md)
- [XML](index.md)
