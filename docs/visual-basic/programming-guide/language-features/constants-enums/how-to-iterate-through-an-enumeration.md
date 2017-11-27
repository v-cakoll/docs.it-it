---
title: 'Procedura: scorrere un''enumerazione in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 439e6eae7d475316625a2cc1d3a70a9e7181f68a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Procedura: scorrere un'enumerazione in Visual Basic
Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i valori delle costanti ai nomi. Per scorrere un'enumerazione, è possibile spostarla in una matrice usando il <xref:System.Enum.GetValues%2A> metodo. È anche possibile scorrere un'enumerazione utilizzando un `For...Each` istruzione, utilizzando il <xref:System.Enum.GetNames%2A> o <xref:System.Enum.GetValues%2A> metodo per estrarre il valore di stringa o numerica.  
  
### <a name="to-iterate-through-an-enumeration"></a>Per scorrere un'enumerazione  
  
-   Dichiarare una matrice in cui convertire l'enumerazione con la <xref:System.Enum.GetValues%2A> metodo prima di passare la matrice si sarebbe qualsiasi altra variabile. Nell'esempio seguente viene visualizzato ogni membro dell'enumerazione <xref:Microsoft.VisualBasic.FirstDayOfWeek> mentre si scorre l'enumerazione.  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-iterate-through-an-enumeration_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulle enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Quando usare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Procedura: Determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Array](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
