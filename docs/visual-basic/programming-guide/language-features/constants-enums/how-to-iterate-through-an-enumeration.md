---
title: "Procedura: Scorrere un'enumerazione"
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: fb6fbdd45ca0e84ccb9fc55296d78e3867d5fe25
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414427"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Procedura: scorrere un'enumerazione in Visual Basic
Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i valori delle costanti ai nomi. Per scorrere un'enumerazione, è possibile spostarla in una matrice usando il <xref:System.Enum.GetValues%2A> metodo. È anche possibile scorrere un'enumerazione usando un' `For...Each` istruzione, usando il <xref:System.Enum.GetNames%2A> metodo o <xref:System.Enum.GetValues%2A> per estrarre la stringa o il valore numerico.  
  
### <a name="to-iterate-through-an-enumeration"></a>Per scorrere un'enumerazione  
  
- Dichiarare una matrice e convertirvi l'enumerazione con il <xref:System.Enum.GetValues%2A> metodo prima di passare la matrice come qualsiasi altra variabile. Nell'esempio seguente vengono visualizzati tutti i membri dell'enumerazione <xref:Microsoft.VisualBasic.FirstDayOfWeek> durante l'iterazione dell'enumerazione.  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle enumerazioni](enumerations-overview.md)
- [Procedura: dichiarare un'enumerazione](how-to-declare-enumerations.md)
- [Quando utilizzare un'enumerazione](when-to-use-an-enumeration.md)
- [Procedura: determinare la stringa associata a un valore di enumerazione](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Procedura: fare riferimento a un membro di enumerazione](how-to-refer-to-an-enumeration-member.md)
- [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
- [Matrici](../arrays/index.md)
