---
title: 'Procedura: Raggruppare i valori delle costanti correlate insieme (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: a4f74e48cfdd5c0bc0f745d0f32eb39442f5bd83
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333328"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>Procedura: Raggruppare i valori delle costanti correlate insieme (Visual Basic)
Un'enumerazione è il modo migliore per raggruppare le costanti correlate tra loro. Per creare un'enumerazione con i `Enum` istruzione nella sezione delle dichiarazioni di una classe o un modulo. Per altre informazioni, vedere [Procedura: Dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).  
  
### <a name="to-group-related-constant-values"></a>Al gruppo di valori delle costanti correlate  
  
1. Scrivere una dichiarazione che include un livello di accesso di codice, il `Enum` (parola chiave) e un nome valido. Questo esempio viene creato il `Private` enumerazione `temperatureValues`.  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. Definire le costanti nell'enumerazione. Questo esempio viene creato il `Public` enumerazione `temperatureValues` e assegna i valori.  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Quando utilizzare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Panoramica sulle costanti](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Tipi di dati costanti e letterali](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)
