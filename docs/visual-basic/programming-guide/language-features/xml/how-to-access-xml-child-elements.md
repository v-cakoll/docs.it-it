---
title: 'Procedura: accedere agli elementi figlio XML (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d3a708b787ad38f08d4673d4003db839f6cf6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
