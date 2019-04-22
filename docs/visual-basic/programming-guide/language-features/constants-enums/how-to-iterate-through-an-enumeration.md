---
title: "Procedura: Scorrere un'enumerazione in Visual Basic"
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 63597145e96b04affc5f0e80e05a56b3fdf27278
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833360"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Procedura: Scorrere un'enumerazione in Visual Basic
Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i valori delle costanti ai nomi. Per scorrere un'enumerazione, è possibile spostarlo in una matrice usando la <xref:System.Enum.GetValues%2A> (metodo). È stato possibile anche scorrere un'enumerazione utilizzando un `For...Each` istruzione, usando il <xref:System.Enum.GetNames%2A> o <xref:System.Enum.GetValues%2A> metodo per estrarre il valore di stringa o numerica.  
  
### <a name="to-iterate-through-an-enumeration"></a>Per scorrere un'enumerazione  
  
-   Dichiarare una matrice e convertire l'enumerazione a esso con il <xref:System.Enum.GetValues%2A> metodo prima di passare la matrice come si sarebbe qualsiasi altra variabile. Nell'esempio seguente consente di visualizzare ogni membro dell'enumerazione <xref:Microsoft.VisualBasic.FirstDayOfWeek> perché viene iterata tramite l'enumerazione.  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Procedura: Dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Quando usare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Procedura: Determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
