---
title: 'Procedura: fare riferimento a un membro di enumerazione'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: 66c527bd4ba4721065de8fca8534fe652d0139be
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414414"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a>Procedura: fare riferimento a un membro di enumerazione (Visual Basic)
Le enumerazioni rappresentano un modo pratico per usare set di costanti correlate e per associare i valori costanti ai nomi. Ad esempio, si può dichiarare un'enumerazione per un set di costanti integer associate ai giorni della settimana e quindi usare i nomi dei giorni anziché i relativi valori integer nel codice.  
  
 È possibile evitare di utilizzare nomi completi con l' `Imports` istruzione. Per altre informazioni, vedere [enumerazioni e qualificazione del nome](enumerations-and-name-qualification.md).  
  
### <a name="to-refer-to-an-enumeration-member"></a>Per fare riferimento a un membro di enumerazione  
  
- Qualificare il nome del membro con l'enumerazione. Nell'esempio seguente, ad esempio, il `Saturday` membro dell'enumerazione viene assegnato `FirstDayOfWeek` alla variabile `DayValue` .  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: dichiarare un'enumerazione](how-to-declare-enumerations.md)
- [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
- [Procedura: scorrere un'enumerazione in Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Procedura: determinare la stringa associata a un valore di enumerazione](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Quando utilizzare un'enumerazione](when-to-use-an-enumeration.md)
